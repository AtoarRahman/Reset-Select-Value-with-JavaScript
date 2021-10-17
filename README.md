## Reset Select Value in JavaScript

```php

<button type="reset" class="btn btn-danger" onclick="resetForm(event, $(this));">Reset</button>

<script>
    function resetForm(e, thisobj) {
        thisform = thisobj.closest('form');
        selectbox_in_form = thisform.find('select');

        // completely remove selected when it has been assigned.
        selectbox_in_form.find('option:selected').removeAttr('selected');
        selectbox_in_form.val('');
        selectbox_in_form.change();

        delete selectbox_in_form;
        delete thisform;
    }
</script>

```
