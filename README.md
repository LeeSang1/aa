

package
com.example.hj;

import
android.app.Activity;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class
MainActivity extends Activity {
 // 1.선언
 EditText e1;
 Button b1;

 @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
       
setContentView(R.layout.activity_main);
        //2.연결
        e1 =
(EditText)findViewById(R.id.editText1);
        b1 =
(Button)findViewById(R.id.button1);
       
        //3.이벤트
        b1.setOnClickListener(new
View.OnClickListener() {
   
   @Override
   public void onClick(View v) {
    // TODO Auto-generated method stub
    //1.사용자가 입력한 날수를 가져온다.
    String days = e1.getText().toString();
    //2.날수를 숫자로 바꾼다.
    int days2 = Integer.parseInt(days);
   //  double days2 = Integer.parseDouble(days);
    //3.날수를 초로 바꾼다.
    int seconds = days2 * 24 * 60 * 60;
    //초 = 날수
*24 *60 * 60
    Toast.makeText(getApplicationContext(),
      "입력한 날수는 "+days+"이고,
"+seconds+"초입니다.",
      Toast.LENGTH_SHORT).show();
    
    
    
   }
  });
    }

 @Override
 public boolean onCreateOptionsMenu(Menu menu) {
  // Inflate the menu; this adds items to the action bar if it is
present.
  getMenuInflater().inflate(R.menu.main, menu);
  return true;
 }

 @Override
 public boolean onOptionsItemSelected(MenuItem item) {
  // Handle action bar item clicks here. The action bar will
  // automatically handle clicks on the Home/Up button, so long
  // as you specify a parent activity in AndroidManifest.xml.
  int id = item.getItemId();
  if (id == R.id.action_settings) {
   return true;
  }
  return super.onOptionsItemSelected(item);
 }
}

<LinearLayout
xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >

   
<TextView
       
android:id="@+id/textView1"
       
android:layout_width="wrap_content"
       
android:layout_height="wrap_content"
        android:text="날수를 입력하시오"
       
android:textAppearance="?android:attr/textAppearanceMedium" />

   
<EditText
       
android:id="@+id/editText1"
       
android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:ems="10" >

       
<requestFocus />
    </EditText>

   
<Button
        android:id="@+id/button1"
        android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:text="결과"
/>

</LinearLayout>



package
com.example.wer;

 

import
android.app.Activity;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;


public class MainActivity extends Activity {
 EditText e1;
 EditText e2;
 EditText e3;
 Button b1;

   
@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
       
setContentView(R.layout.activity_main);
        e1 =
(EditText)findViewById(R.id.editText1);
        e2 =
(EditText)findViewById(R.id.editText2);
        e3 = (EditText)findViewById(R.id.editText3);
        b1 =
(Button)findViewById(R.id.button1);
       
        b1.setOnClickListener(new
View.OnClickListener() {
   
   @Override
   public void onClick(View v) {
    // TODO Auto-generated method stub
    String kor = e1.getText().toString();
    String eng = e2.getText().toString();
    String math = e3.getText().toString();
    
    int kor2 = Integer.parseInt(kor);
    int eng2 = Integer.parseInt(eng);
    int math2 = Integer.parseInt(math);
    
    int total = kor2 + eng2 + math2;
    
    double avg = Double.parseDouble( String.format(
"%.1f" , total / 3.0 ));
    Toast.makeText(getApplicationContext(),
      "총합은"+total+"이며 평균은
"+avg+"입니다.",
      Toast.LENGTH_SHORT).show();
    
   }
  });
    }

   
@Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items
to the action bar if it is present.
       
getMenuInflater().inflate(R.menu.main, menu);
        return true;
    }

   
@Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle action bar item clicks
here. The action bar will
        // automatically handle clicks on
the Home/Up button, so long
        // as you specify a parent activity
in AndroidManifest.xml.
        int id = item.getItemId();
        if (id == R.id.action_settings) {
            return true;
        }
        return
super.onOptionsItemSelected(item);
    }
}

<LinearLayout
xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >

   
<TextView
       
android:id="@+id/textView1"
       
android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="국어점수는?"
       
android:textAppearance="?android:attr/textAppearanceMedium" />

   
<EditText
       
android:id="@+id/editText1"
       
android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:ems="10" >

       
<requestFocus />
    </EditText>

   
<TextView
       
android:id="@+id/textView2"
       
android:layout_width="wrap_content"
       
android:layout_height="wrap_content"
        android:text="영어점수는?"
        android:textAppearance="?android:attr/textAppearanceMedium"
/>

   
<EditText
       
android:id="@+id/editText2"
       
android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:ems="10" />

   
<TextView
        android:id="@+id/textView3"
       
android:layout_width="wrap_content"
       
android:layout_height="wrap_content"
        android:text="수학점수는?"
       
android:textAppearance="?android:attr/textAppearanceMedium" />

   
<EditText
       
android:id="@+id/editText3"
        android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:ems="10" />

   
<Button
        android:id="@+id/button1"
       
android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:text="결과"
/>

</LinearLayout>



package
com.example.fdsgsd;

import
android.app.Activity;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;


public class MainActivity extends Activity {
 EditText e1;
 Button b1;
 

   
@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
       
        e1 =
(EditText)findViewById(R.id.editText1);
        b1 =
(Button)findViewById(R.id.button1);
       
        b1.setOnClickListener(new
View.OnClickListener() {
   
   @Override
   public void onClick(View v) {
    // TODO Auto-generated method stub
    String bytes = e1.getText().toString();
    int bytes3 = Integer.parseInt(bytes);
    int meagbytes = bytes3 *1024;
    long kilobytes = meagbytes * 1024;
    long bytes2 = kilobytes * 1024;
    Toast.makeText(getApplicationContext(),
      ""+meagbytes+"메가바이트,
"+kilobytes+"킬로바이트, "+bytes2+"바이트입니다.",
      Toast.LENGTH_SHORT).show();
    
   }
  });
    }

   
@Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items
to the action bar if it is present.
       
getMenuInflater().inflate(R.menu.main, menu);
        return true;
    }

   
@Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle action bar item clicks
here. The action bar will
        // automatically handle clicks on
the Home/Up button, so long
        // as you specify a parent activity
in AndroidManifest.xml.
        int id = item.getItemId();
        if (id == R.id.action_settings) {
            return true;
        }
        return
super.onOptionsItemSelected(item);
    }
}

<LinearLayout
xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >

   
<TextView
       
android:id="@+id/textView1"
       
android:layout_width="wrap_content"
       
android:layout_height="wrap_content"
        android:text="파일의 용량을 기가바이트 단위로 입력"
        android:textAppearance="?android:attr/textAppearanceMedium"
/>

   
<EditText
       
android:id="@+id/editText1"
       
android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:ems="10" >

       
<requestFocus />
    </EditText>

   
<Button
        android:id="@+id/button1"
       
android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:text="결과"
/>

</LinearLayout>



package
com.example.dfsgasf;

import
android.app.Activity;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;


public class MainActivity extends Activity {
 EditText e1;
 EditText e2;
 EditText e3;
 Button b1;

   
@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
       
setContentView(R.layout.activity_main);
        e1 =
(EditText)findViewById(R.id.editText1);
        e2 = (EditText)findViewById(R.id.editText2);
        e3 =
(EditText)findViewById(R.id.editText3);
        b1 =
(Button)findViewById(R.id.button1);
       
        b1.setOnClickListener(new
View.OnClickListener() {
   
   @Override
   public void onClick(View v) {
    // TODO Auto-generated method stub
    String coffe = e1.getText().toString();
    String milk = e2.getText().toString();
    String gocoffe = e3.getText().toString();
    
    int coffe2 = Integer.parseInt(coffe);
    int milk2 = Integer.parseInt(milk);
    int gocoffe2 = Integer.parseInt(gocoffe);
    
    int total = coffe2*200 + milk2*300 + gocoffe2*500;
    
    Toast.makeText(getApplicationContext(),
      "총 주문금액은 "+total+"입니다.",
      Toast.LENGTH_SHORT).show();
    
   }
  });
    }

   
@Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items
to the action bar if it is present.
       
getMenuInflater().inflate(R.menu.main, menu);
        return true;
    }

   
@Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle action bar item clicks
here. The action bar will
        // automatically handle clicks on
the Home/Up button, so long
        // as you specify a parent activity
in AndroidManifest.xml.
        int id = item.getItemId();
        if (id == R.id.action_settings) {
            return true;
        }
        return
super.onOptionsItemSelected(item);
    }
}

<LinearLayout
xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >

   
<TextView
       
android:id="@+id/textView1"
       
android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="커피개수는?"
       
android:textAppearance="?android:attr/textAppearanceMedium" />

   
<EditText
       
android:id="@+id/editText1"
       
android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10" >

       
<requestFocus />
    </EditText>

   
<TextView
       
android:id="@+id/textView2"
       
android:layout_width="wrap_content"
       
android:layout_height="wrap_content"
        android:text="우유개수는?"
       
android:textAppearance="?android:attr/textAppearanceMedium" />

   
<EditText
       
android:id="@+id/editText2"
       
android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:ems="10" />

   
<TextView
        android:id="@+id/textView3"
       
android:layout_width="wrap_content"
       
android:layout_height="wrap_content"
        android:text="고급커피개수는?"
       
android:textAppearance="?android:attr/textAppearanceMedium" />

   
<EditText
        android:id="@+id/editText3"
       
android:layout_width="match_parent"
       
android:layout_height="wrap_content"
        android:ems="10" />

   
<Button
        android:id="@+id/button1"
       
android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="결과"
/>

</LinearLayout>



 

 

