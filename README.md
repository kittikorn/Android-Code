## Android Code

### All in one
*Notification with show

        //Notification
        Button cmdNoti = (Button)findViewById(R.id.button2);
        cmdNoti.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View arg0) {
                Intent i = new Intent(MainActivity.this,UpdateActivity.class);
                PendingIntent pI = PendingIntent.getActivity(MainActivity.this, 0, i, 0);
                Bitmap bmp = BitmapFactory.decodeResource(getResources(),R.drawable.ic_launcher);
                NotificationCompat.Builder nb = new NotificationCompat.Builder(MainActivity.this)
                        .setSmallIcon(R.drawable.ic_launcher)
                        .setLargeIcon(bmp).setTicker("มีอัพเดตใหม่")
                        .setContentTitle("Android L จ้า")
                        .setContentText("Google มาแว้วจ้าาาาาาาาาาา")
                        .setContentIntent(pI).setAutoCancel(true);
                Notification n =  nb.build();
                nManager = (NotificationManager) getSystemService(NOTIFICATION_SERVICE);
                nManager.notify(NOTIFICATION_ID,n);
            }
        });

*Message Dialog

        //Message Dialog
        final AlertDialog.Builder dia = new AlertDialog.Builder(this);
        Button cmd = (Button) findViewById(R.id.button2);
        cmd.setOnClickListener(new View.OnClickListener() {
                                   public void onClick(View v) {
                                       dia.setTitle("Hello");
                                       dia.setMessage("World");
                                       dia.setNegativeButton("No", null);
                                       dia.setPositiveButton("Yes", new AlertDialog.OnClickListener()
                                       {
                                           public void onClick(DialogInterface dialog,int arg1)
                                           {
                                               String a = "Hello";
                                               String b = "Pame";
                                               Toast.makeText(MainActivity.this,"บันทึกข้อมูลแล้วจ้า"+b,Toast.LENGTH_LONG).show();
                                           }
                                                                                  });
                                       dia.show();
                                   }
                               }
        );

*Toast
                
`        //Toast.makeText(MainActivity.this, "สวัสดี", Toast.LENGTH_LONG).show();`
