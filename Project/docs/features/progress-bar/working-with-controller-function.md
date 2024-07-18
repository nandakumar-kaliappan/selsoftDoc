---
description: Can be used when the message need to be updated from Controller
---

# Working with Controller function

### JS

In your entry form ajax call:

{% code title="MyEntryForm.js" %}
```javascript
         
    // inside some function
    si.loadJS("scripts/jquery.signalR-2.2.2.min.js", function () {            
        si.loadJS("signalr/hubs", function () {
            sd.startProgess();
            ajaxPost(entryId + '/TestStatusBar', {}, function (res) {
                if (res.error == undefined) {
                    sd.startProgess()
                    jI("progressBar").hide();
                    jSF("#progressBar div").css({ "width": "0%" }).innerHTML = "0 %";
                } else {
                    alertify.error(res.error);
                    console.error(res.message);
    
                }
            });
        });
    });
```
{% endcode %}



### C\#

In controler, use the method

```csharp
RealTimeProgressBar.ProgressHub.sendProgress(string Message, Double Percentage);
```

{% code title="MyEntryForm.cs" %}
```csharp
        [HttpPost]
        public void TestStatusBar() {
            for (int i = 0; i < 7; i++) {
                double completionPercentage = Math.Round(Convert.ToDouble(i * 100 / (7)));
                RealTimeProgressBar.ProgressHub.sendProgress("Work under Progress", completionPercentage);
                Thread.Sleep(2000);
            }
            
        }
```
{% endcode %}
