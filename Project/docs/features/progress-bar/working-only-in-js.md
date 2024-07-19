---
description: >-
  If the Progress bar need to be updated in some JS function alone use the
  following code
---

# Working only in JS - Progress Bar

### Show the Progress Bar

* `jI("progressBar").css({ "display": "block", "z-index": "99999999" }).center();`

### Update the Progress Bar

* `sd.updateProgress("New Data",33)`

This command will update the message as `New Data` and with `33%` completion

<figure><img src="../../.gitbook/assets/progressbar.PNG" alt=""><figcaption></figcaption></figure>

### Close the Progress Bar

```javascript
jI("progressBar").hide();
jSF("#progressBar div").css({ "width": "0%" }).innerHTML = "0 %";
```

These command will reset the progress bar and hides them
