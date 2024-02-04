```cs
public void OnPointerClick(PointerEventData eventData)
    {
        // 아이템이 가방이라면 해당 가방의 UI 출력
        if (eventData.pointerDrag.GetComponent<Slot>().ItemStatus)
        {
            if (ItemStatus.ItemName == "Bag")
            {
                if (!BagInventory.activeSelf)
                {
                    Select.transform.SetAsLastSibling();
                    BagInventory.SetActive(true);
                }
            }
        }
    }
```

## 클릭 한 정보 eventData에서 eventData.pointerDrag.GetComponent<Slot>().ItemStatus을 이용하여 Null값을 예외 처리를 하여 NullReferenceException: Object reference not set to an instance of an object 오류를 해결 하였음
