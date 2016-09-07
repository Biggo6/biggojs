[![biggojs.png](https://s12.postimg.org/owpt9q2bh/biggojs.png)](https://postimg.org/image/8lppdeptl/)
# BiggoJs - humanize jquery and php together

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

Example using with Laravel withoud file upload
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


