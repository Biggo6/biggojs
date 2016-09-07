[![biggojs.png](https://s12.postimg.org/owpt9q2bh/biggojs.png)](https://postimg.org/image/8lppdeptl/)
# BiggoJs - humanize the interaction between jquery and php apps i.e Laravel framework apps 

the library that enhances humanly way  of programming php apps using jquery
it was written on top of jquery methods

# Installation 

<p>BiggoJs depends on jquery first include jquery before biggo.js file</p>

`<script src="//code.jquery.com/jquery.js"></script>`

<p>Then follows biggo.js </p>

### Use this URL in production

`<script src="https://cdn.rawgit.com/Biggo6/biggojs/master/biggo.js"></script>`

### Use this URL for development

`<script src="https://rawgit.com/Biggo6/biggojs/master/biggo.js"></script>`

### Usage
##### 1. Jquery Ajax Method
`<script src="//code.jquery.com/jquery.js"></script>`
`<script src="https://rawgit.com/Biggo6/biggojs/master/biggo.js"></script>`
.....
.....
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
    "firstname" : "Joram",
    "lastname"  : "Kimata",
    "email"     : "jkimata@biggojs.com"
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

In Laravel Codes

<?php


if (Input::hasFile('photo')) {
    // working with photo
} 


```

# Contribution

You are invited to contribute to this library in the following section :- <i>good documentation, code refactoring and coding your ideas </i> 


