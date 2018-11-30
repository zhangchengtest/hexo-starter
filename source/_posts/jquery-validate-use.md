title: 'jquery validate use '
date: 2017-01-12 11:03:38
tags:
---
title: 'jquery validate use '
tags:
---
```html
	<div class="form-group form-group-lg" >
				<label class="control-label" for="amount">Order Amount
                </label>
                <div class="input-group">
					<span class="input-group-addon">$</span>
					<input class="form-control" onclick="this_input(this)" id="amount" name="amount"  placeholder="Amount" minlength="2" required
						/>
				</div>
				<div class="error-msg" style="color:red"></div>
            </div>


```

```script


	$.validator.setDefaults({
			    submitHandler: function() {
			      alert("提交事件!");
			    }
			});

			$(document).ready(function () {
				$('#form_1').validate({
					errorPlacement:function(error,element) {  
						error.appendTo(element.parent("div").next("div"));
					}
				});
			});
            
```