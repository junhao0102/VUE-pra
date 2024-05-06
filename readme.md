# Vue 沒有為陣列提供 setter 和 getter。
### 無法直接通過索引操作陣列，只有以下方法可以讓模板重新解析：

- `push()`: 在陣列末尾添加一個或多個元素。
- `pop()`: 移除並返回陣列的最後一個元素。
- `shift()`: 移除並返回陣列的第一個元素。
- `unshift()`: 在陣列的開頭添加一個或多個元素。
- `splice()`: 通過刪除或替換現有元素或添加新元素來修改陣列的內容。
- `sort()`: 對陣列元素進行排序。
- `reverse()`: 將陣列中的元素倒置。
```bash
$ vm.$set(vm.XXX,index,value)
```
這些方法的使用會觸發 Vue 檢測到陣列的變化，並重新解析模板。


# Vue.js 組件生命週期

## 創建階段

- **beforeCreate**
  - 在實例初始化之後，但在實例被創建之前調用，此時數據觀察和事件/監聽器設置尚未完成，因此無法訪問 `data` 和 `methods`。
- **created**
  - 在實例創建完成後立即調用，此時已經完成數據觀察，屬性和方法的運算，但掛載階段尚未開始，`$el` 屬性目前不可見。

## 掛載階段

- **beforeMount**
  - 在掛載開始之前被調用。此時，相關的 render 函數首次被調用，實際的 DOM 尚未生成。

## 更新階段

- **beforeUpdate**
  - 在數據變化後，還不會渲染頁面(頁面和數據不同步)。
- **updated**
  - 在由於數據的變化重新渲染，數據和頁面同步。

## 銷毀階段

- **beforeDestroy**
  - 在實例銷毀之前調用。在這一步，實例仍然完全可用，但無法改變 `data`
- **destroyed**
  - 在實例銷毀後調用。此時，所有的事件監聽器已被移除，子實例也都被銷毀。
