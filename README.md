package com.profilo.ledapp;

import android.os.Bundle;
import android.app.Activity;
import android.view.Menu;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends Activity {

	Button btnGiris; // BUTONUN ID'si
	EditText etKadi, etSifre; // TEXTBOX'ın ID'si
	
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        
        btnGiris = (Button)findViewById(R.id.btnGiris);
        etKadi   = (EditText)findViewById(R.id.etKadi);
        etSifre  = (EditText)findViewById(R.id.etSifre);
        
        btnGiris.setOnClickListener(new View.OnClickListener() {
			
			public void onClick(View v) {
				// TODO Auto-generated method stub
				if(etKadi.getText().toString().equals("admin") && etSifre.getText().toString().equals("123456")){
					Toast.makeText(getApplicationContext(), "Giriş başarıyla tamamlandı !", Toast.LENGTH_LONG).show();
				}else if(etKadi.getText().toString().equals("") || etSifre.getText().toString().equals("")){
					Toast.makeText(getApplicationContext(), "Boş alanları doldurunuz !", Toast.LENGTH_LONG).show();
				}else{
					Toast.makeText(getApplicationContext(),"Giriş bilgileriniz yanlış !", Toast.LENGTH_LONG).show();
				}
			}
		});
        
    }


    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        getMenuInflater().inflate(R.menu.main, menu);
        return true;
    }
    
}
