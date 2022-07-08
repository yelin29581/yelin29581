function doGet(){
  return HtmlService.createTemplateFromFile('index').evaluate()
.addMetaTag('viewport', 'width=device-width, initial-scale=1")
 .setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)
}
function getData(){
const ss = SpreadsheetApp.getActiveSpreadsheet()
const ws = ss.getSheetByName('1')
const dataRange = ws.getRange('A1').getDataRegion()
const data = dataRange.getDisplayValues()
  
const headers = data. shift()
  
const tabledata = data.map(r =>{ 
  const tempObject = {}
  headers.forEach((header,1) => {
    tempObject[header] = r[i]
  })
  return tempObject
 })
console.log(tabledata)
return tabledata
}
