# qr-code-generator-app



Naming Edit text ,Button and image view 
                        
                        EditText etInput;
                        Button bt_generate;
                        ImageView iv_output;

seting opening page as activity_main.xml
   setContentView(R.layout.activity_main);

Defining  Edit text ,Button and image view by id

                etInput = findViewById(R.id.et_input);
                bt_generate = findViewById(R.id.bt_generate);
                iv_output = findViewById(R.id.iv_output);

 opening on click listener for button 
         
         bt_generate.setOnClickListener(new View.OnClickListener() {
         getting input from edit txt and saving it to a variable called sText 
                           
                           //String sText = etInput.getText().toString().trim();
 
 
creating object for multi form writer
 
     MultiFormatWriter writer = new MultiFormatWriter();

      setting Bit Metrix for qr code ,setting 350*350 size
     BitMatrix matrix = writer.encode(sText, BarcodeFormat.QR_CODE, 350, 350);

 
 #creating an object for QR code encoder  
                                
                                BarcodeEncoder encoder = new BarcodeEncoder();
                                #passing metrix into encoder and getting out as an bitmap
                                Bitmap PIC = encoder.createBitmap(matrix);
                                #setting pic bitmap to image view 
                                iv_output.setImageBitmap(PIC);

SNAPSHOTS: 
                    


