---
description: >-
  Add a feature to highlight the side bar menu item corresponding to the current
  entry/master form
cover: ../.gitbook/assets/Activation  of Sidebar Menu Item.PNG
coverY: 0
---

# Activation of Sidebar Menu Item of Current Page

* In the entry .js file _`onSetPage()`_ include the following code

### **Transactions:**

{% code title="someTransactionForm.js" %}
```javascript
onSetPage() {
        jS("#navbar_transactions,#mnu" + entryId + trnType).addClass('active');
        jSF("#navbar_transactions>a").addClass("open");
        jSF("#navbar_transactions ul").addClass("show");
        ...
```
{% endcode %}

### **Masters**:

{% code title="someMasterForm.js" %}
```javascript
onSetPage() {
        jS("#navbar_master,#mnu" + entryId + trnType).addClass('active');
        jSF("#navbar_master>a").addClass("open");
        jSF("#navbar_master ul").addClass("show");
        ...
```
{% endcode %}

### **Important**

Make sure that menu name is having this format `#mnu" + entryId + trnType`

example `#mnuSomeEtryFormSEF`

