# JQuery Ajax POST request from form

.HTML

```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
<form class="form-signin" role="form" id="emailform" action="request.php" method="post"
  name="emailform">
  	<input type="name" id="name" name="name"/>
    <input type="email" id="email" name="email"/> <button name="submit"
    class="btn btn-lg btn-primary btn-block" type="submit">Get New Code</button>
</form>
```

JS

```
    $(document).ready(function() {
        
        //THIS ALERT FIRES WHEN THE PAGE LOADS
        //NOT WHEN A BUTTON IS CLICKED
        alert('jquery');
      
         $.ajax({
                url: '/registerMetadata',
                dataType: 'json',
                type: 'POST',
                contentType: 'application/json',
                data: JSON.stringify( { "email": $('#email').val(), "name": $('#name').val() } ),
                processData: false,
                success: function( data, textStatus, jQxhr ){
                    console.log(data)
                },
                error: function( jqXhr, textStatus, errorThrown ){
                    console.log( errorThrown );
                }
            });
    });
```