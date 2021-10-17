## Reset Select Value with JavaScript

```php
<form method="get" onsubmit="return testFormSubmit($(this));">
    <input type="hidden" name="somehidden" value="hidden input for test many form fields.">
    <select name="selectbox" class="selectbox-replacement-enabler test-form-submit-selectbox form-control">
        <option value="">Please select</option>
        <option value="ajax">Ajax</option>
        <option value="json">Json</option>
        <option value="jquery">jQuery</option>
        <option value="php">PHP</option>
        <option value="html">HTML</option>
    </select>
    <select name="selectbox2" class="selectbox-replacement-enabler test-form-submit-selectbox form-control">
        <option value="">Please select</option>
        <option value="ajax">Ajax</option>
        <option value="json">Json</option>
        <option value="jquery">jQuery</option>
        <option value="php">PHP</option>
        <option value="html" selected="selected">HTML</option>
    </select>
    <button type="submit" class="btn btn-primary">Submit</button>
    <button type="reset" class="btn btn-default" onclick="resetForm(event, $(this));">Reset</button>
</form>

```
```php
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
