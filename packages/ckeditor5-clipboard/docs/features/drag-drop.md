---
menu-title: Drag and drop
meta-title: Drag and drop | CKEditor 5 Documentation
meta-description: Learn all about using the drag and drop mechanism to manage content and uploads in CKEditor 5
category: features
---

{@snippet features/build-drag-drop-source}

# Drag and drop

The drag and drop feature lets you drag and drop both text and content blocks such as paragraphs, tables, or lists inside the editor. This allows you to select an entire block or multiple blocks, and move them before or after other blocks. You can also drag and drop HTML and plain text content from outside the editor and use it to upload images.

## Demo

The demo below lets you drag contacts from the list to the editor. The contacts are inserted into the editor as custom widgets representing the [h-card microformat](http://microformats.org/wiki/h-card). You can also select and drag around existing content inside the editor.

{@snippet features/drag-drop}

Photos: [Wikipedia.org](http://en.wikipedia.org).

<info-box info>
	This demo only presents a limited set of features. Visit the {@link examples/builds/full-featured-editor feature-rich editor example} to see more in action.
</info-box>

The source code of the above snippet is available here: [`drag-drop.js`](https://github.com/ckeditor/ckeditor5/tree/master/packages/ckeditor5-clipboard/docs/_snippets/features/drag-drop.js), [`drag-drop.html`](https://github.com/ckeditor/ckeditor5/tree/master/packages/ckeditor5-clipboard/docs/_snippets/features/drag-drop.html).

## File upload via drag and drop

When the {@link features/ckbox CKBox file manager} is enabled in your CKEditor&nbsp;5 integration, you can upload files and images using the drag and drop mechanism. You can test this solution in the {@link features/ckbox#demo CKBox demo}.

## Drag and drop of content blocks

Since v40.0.0, the drag and drop plugin fully supports dragging content blocks such as paragraphs, tables, or lists inside the editor by default. This allows you to select an entire block or multiple blocks, and move them before or after other blocks.

The drag and drop functions include:

* Selection of the text, elements, multiple blocks, and moving these around.
* Placement of blocks inside other blocks such as tables, blockquotes, etc.
* The braille dots panel icon {@icon @ckeditor/ckeditor5-core/theme/icons/drag-indicator.svg Drag indicator}  in the [balloon block editor](#balloon-block-editor-demo) now behaves as a drag handle.

### Classic editor demo

Select a block or blocks, and drag them across the document. You can place blocks inside other blocks, such as tables and blockquotes.

{@snippet features/block-drag-drop}

### Balloon block editor demo

In the balloon block editor, you can also drag content blocks using the drag handle. Select or focus on the block, and then drag the block with the braille dots panel icon {@icon @ckeditor/ckeditor5-core/theme/icons/drag-indicator.svg Drag indicator}.

{@snippet features/block-balloon-drag-drop}

## Installation

<info-box info>
	This feature is required by the clipboard plugin and is enabled by default in all {@link installation/getting-started/predefined-builds predefined builds}. These installation instructions are for developers interested in building their own custom rich-text editor.
</info-box>

To add this feature to your rich-text editor, install the [`@ckeditor/ckeditor5-clipboard`](https://www.npmjs.com/package/@ckeditor/ckeditor5-clipboard) package:

```
npm install --save @ckeditor/ckeditor5-clipboard
```

Then add the {@link module:clipboard/clipboard~Clipboard `Clipboard`} plugin to your plugin list:

```js
import { Clipboard } from '@ckeditor/ckeditor5-clipboard';

ClassicEditor.create( document.querySelector( '#editor' ), {
	plugins: [ Clipboard, Bold, /* ... */ ],
})
	.then( /* ... */ )
	.catch( /* ... */ );
```

The {@link module:clipboard/dragdrop~DragDrop `DragDrop`} plugin will activate along with the clipboard plugin.

## Styling the drag and drop

The drag and drop target line color is managed by the CSS variable (`--ck-clipboard-drop-target-color`). You can use the following snippet to change the color of the line:

```css
:root {
	--ck-clipboard-drop-target-color: green;
}
```

## Related features

* CKEditor&nbsp;5 supports dropping images from the file system thanks to the {@link features/image-upload image upload} feature.

## Contribute

The source code of the feature is available on GitHub at [https://github.com/ckeditor/ckeditor5/tree/master/packages/ckeditor5-clipboard](https://github.com/ckeditor/ckeditor5/tree/master/packages/ckeditor5-clipboard).
