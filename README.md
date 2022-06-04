# SmartcatMultipleSegmentsPaste

To paste the clipboard content (multiple paragraphs or table cells) into multiple segments in Smartcat interface, create a bookmark in your Web browser (I've tested in Chrome only), enter any name you want.

In URI field, enter the following code:

javascript:(function(){navigator.clipboard.readText().then(clipboardText=>{clipboardArray=clipboardText.split(/[\r\n]+/g);for(i=0;i<clipboardArray.length;i++){statement='document.activeElement.closest("tbody")'+'.nextElementSibling'.repeat(i)+'.getElementsByClassName("l-content-editor__view l-content-editor__view_editor")[1].innerText=clipboardArray[i]';eval(statement);}})})();

Save to apply the changes.

Copy a list or multiple paragraphs to clipboard (I've tried copying from txt, docx, xlsx, and pdf).

In Smartcat interface, place cursor to the segment you want to start pasting from, and click the bookmark you've created.

The pasted content won't be saved to your document unless you commit any editing in every segment you've pasted to.
