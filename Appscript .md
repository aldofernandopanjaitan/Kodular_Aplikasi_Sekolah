

Langkah pembuatan Appscript untuk memberikan akses Upload Gambar ke Google Drive
<img width="845" height="272" alt="image" src="https://github.com/user-attachments/assets/c2553895-2609-4966-980c-9d118dfb7fff" />
<img width="258" height="274" alt="image" src="https://github.com/user-attachments/assets/656af8e1-1dbd-40f1-b223-af4c6369c539" />
<img width="708" height="675" alt="image" src="https://github.com/user-attachments/assets/84ed9186-63ea-422d-b721-1974e72f6f31" />
<img width="371" height="199" alt="image" src="https://github.com/user-attachments/assets/2166b7f4-a930-4f68-a5cb-a135ad1c7fa9" />
<img width="371" height="199" alt="image" src="https://github.com/user-attachments/assets/7c3fa4b0-9756-47c6-b13d-e49b9a0c955e" />

<img width="1479" height="913" alt="image" src="https://github.com/user-attachments/assets/502e7a7a-9292-4186-8e1b-7bb12ec6e5d7" />
<img width="1251" height="522" alt="image" src="https://github.com/user-attachments/assets/f133a541-8476-4617-9ff9-206fe2f62baa" />
<img width="514" height="260" alt="image" src="https://github.com/user-attachments/assets/f08d6513-f6c3-4ec0-92a3-aeca1189f768" />
<img width="608" height="435" alt="image" src="https://github.com/user-attachments/assets/06477315-2c84-4cf4-a596-f9c896002423" />
<img width="514" height="260" alt="image" src="https://github.com/user-attachments/assets/33ec591b-50c6-4539-8ce2-4b6c17492190" />
<img width="730" height="357" alt="image" src="https://github.com/user-attachments/assets/13b0fe8b-15bf-42b8-891d-ac01ba309d95" />
<img width="497" height="187" alt="image" src="https://github.com/user-attachments/assets/56b447ee-0c03-49b6-ab1f-46ae45de7930" />
<img width="360" height="149" alt="image" src="https://github.com/user-attachments/assets/6270d782-dbe9-48c8-9b32-224e77486b98" />
<img width="308" height="107" alt="image" src="https://github.com/user-attachments/assets/418ab3cc-e45d-4e8a-8d3e-2967df6336c8" />
<img width="640" height="95" alt="image" src="https://github.com/user-attachments/assets/1d5f999b-d3a4-411c-884c-f1b71c9218d9" />
<img width="659" height="631" alt="image" src="https://github.com/user-attachments/assets/658373a9-9d01-4bea-9c77-e5f946930015" />
<img width="707" height="556" alt="image" src="https://github.com/user-attachments/assets/a8998380-e170-48e7-bf70-f8a2f1f17a95" />


#[Kode Appscript yg perlu disalin : ]

function doPost(e) {
  var data = Utilities.base64Decode(e.parameters.data); //filestring
  var blob = Utilities.newBlob(data, e.parameters.mimetype, e.parameters.filename); //mimetype dan filename
  var fileid = DriveApp.getFolderById(e.parameters.folderid).createFile(blob).getId(); //upload ke google drive dengan folderid
  
  if(fileid){
	  return ContentService.createTextOutput("File sukses ter-upload");
	}
  else{
	  return ContentService.createTextOutput("File gagal ter-upload");
  }
}
