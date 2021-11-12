# Tag Helpers

Partial
    asynchronously render a partial view:

    <partial name="_ValidationScriptsPartial" />
    is the same as:
    @{await Html.RenderPartialAsync("_ValidationScriptsPartial");}

Label
    extends the standard HTML <label> element.
    uses an asp-for attribute. The attribute accepts a specified PageModel property

Input

    <input asp-for="NewPizza.Name" class="form-control" />
    turns into
    <input name="NewPizza.Name" class="form-control" id="NewPizza_Name" type="text" value="" data-val-required="The Name field is required." data-val="true">

    
    Provides client-side validation using jQuery, based on the model's data annotation attributes provided through the PageModel.


Validation Summary Message

    <div asp-validation-summary="All"></div>
    turns into
    <input name="NewPizza.Price" class="form-control" id="NewPizza_Price" type="text" value="" data-val-required="The Price field is required." data-val="true" data-val-range-min="0.01" data-val-range-max="9999.99" data-val-range="The field Price must be between 0.01 and 9999.99." data-val-number="The field Price must be a number.">

