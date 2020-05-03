# BiggoJs 

###### Using jQuery Behind the scene

# Installation 

<p>BiggoJs depends on jquery first include jquery before biggo.js file</p>

`<script src="//code.jquery.com/jquery.js"></script>`

<p>Then follows biggo.js </p>




### Usage
##### 1. Jquery Ajax Method
```
<script src="//code.jquery.com/jquery.js"></script>
<script src="/js/biggo.js"></script>

```

```javascript
<script>
$(function(){
    var biggo = Biggo.talkToServer(url, data, isFileUpload=false, method='post', dataType='text', el=null,type='post');
    biggo.then(function(res){
        // work with result from server
    });
});
</script>

```

A.Example using with Laravel without file upload
------

```javascript
<script>

var url = '{{route("users.store")}}';
var data = {
    "firstname" : "Joe",
    "lastname"  : "Doe",
    "email"     : "joedoe@biggojs.com"
}
$(function(){
    var biggo = Biggo.talkToServer(url, data);
    biggo.then(function(res){
        // work with result from server
    });
});
</script>
```

B.Example using with Laravel with file upload
------

```
<form id="userForm">
.....
.....
<input type="file" name="photo" id="photo" />
.......
....
</form>
```

````javascript
<script>

            var isFileUpload = false;
            var data;
            if(Biggo.isFileValueSetted(photo) != undefined){
                var arr  = Biggo.serializeData(userForm);
                var arr2 = ["photo"];
                isFileUpload = true;
                data = Biggo.prepareFormData(arr, arr2);
            }else{
                data = Biggo.serializeData(userForm);
            }

           
            Biggo.talkToServer('{{route("users.store")}}', data, isFileUpload).then(function(res){
                
                
                if(res.error){
                    Biggo.showFeedBack(userForm, res.msg, res.error);
                }else{
                    if(register == "save"){
                        window.location = "{{route('users.redirectWith')}}";
                    }else{
                        $('#form_reg')[0].reset();
                        Biggo.showFeedBack(userForm, res.msg, res.error);
                    }
                                                                                                                                                                                                                                                                                                                      
                }
            });
            

</script>
```

# In Laravel Codes
------

```
<?php


if (Input::hasFile('photo')) {
    // working with photo
} 


```




