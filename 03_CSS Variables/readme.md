# 03 - **CSS Variables**
>編於：2019/03/24   

## **Topic**
建立一個直接改變CSS Variable的介面，可調整的有padding、模糊度、顏色。

## **Steps**
#### Step1.
利用HTML tag，建立controls。`<label>`來設定文字敘述，`<input>`來設定輸入的內容(有好幾種type: button, range, color, text...)。for通常設定與input的name相同。
#### Step2.
用`querySelectorAll()`抓下inputs，使用`forEach()`讓每個值都能使用監聽事件。
這邊的監聽事件可以採用`change`或`mouseover`事件，來跑function.
`change`事件是指input中的value被改變，拖曳放開後，才有效果；`mouseover`事件讓在拖曳滾輪的同時，即有反應。

#### Step3.
function主要就是進到style裡改變Variable的值。
`style.setProperty("padding", "10px")`，在這邊padding以CSS中，:root的方式寫，如--base。this此時是input，所以input的name是跟CSS裡Variable設定是一樣的才可以這樣用。
因為this.value本身沒有帶單位，所以要另外讀取先前在HTML設的`data-*`來使用(這邊用`.dataset.*`)。若沒有值則設定為空的，否則會出現undefined.
```
    function updateChange() {
      const suffix = this.dataset.sizing || "";
      document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
    }
```


## **JS Remarks**
### **1. :root{ }**：


>Ref：[MDN-Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)

### **2. document.documentElement**：

### **3. style.setProperty**：

### **4. mousemove事件**：
## Others
