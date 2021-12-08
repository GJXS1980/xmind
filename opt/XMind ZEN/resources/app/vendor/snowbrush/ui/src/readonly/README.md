# snowbrush (readonly)

```javascript
var snowbrush = require('snowbrush')
import snowbrush from 'snowbrush'
```

## snowbrush.createWorkbookEditor(content: string|ArrayBuffer|Uint8Array|Buffer|Blob, container: Element, options?: [Options](#Options)): [WorkbookEditor](#WorkbookEditor)

Create a workbook editor of snowbrush

### WorkbookEditor

#### we.switchSheetTo(index: number): void

Init and show sheet

#### we.getSheetsCount(): number

#### we.getSheetTitle(index: number): string

#### we.collapseBranch(): void

#### we.extendBranch(): void

#### we.zoom(scale: number): void

#### we.close(): void

```js
fs.readFileAsync(filePath).then(fileContent=>{
  let container = document.createElement('div')
  container.classList.add('editor-container')
  body.appendChild(container)

  let options = {
    languageCode: 'zh-CN',
    resourceUrlPrefix: '/'
  }

  snowbrush.createWorkbookEditor(content,container,options).then(we=>{
    we.switchSheetTo(0)
  }).catch(e=>{
      if(e == 'PasswordError'){
        options.password = 'test'
        snowbrush.createWorkbookEditor(content,container,options).then(we=>{
          we.switchSheetTo(0)
        })
      } else {
        console.log('')
      }
  })
})
```

#### Options

|  Options  |   Value   |     Description     |
| --------- | --------- | ------------------- |
| type | `xmind`, `lighten`, `freemind`, `mindmanager` | when type is `freemind`, `content` MUST be string |
| language | `en-US`, `zh-HK`, `zh-TW`, `ja-jp`, `de-DE`, `fr-FR` |  |
| resourcesUrlPrefix | url | Indicate root directory that can find all resources such as `images/*`, `markers/*` |
| password | string | password of encrypted `xmind` file |
