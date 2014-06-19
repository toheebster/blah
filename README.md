blah
====

CalendarView

package com.toe.checity;

import java.io.File;

import java.util.Calendar;
import java.util.Date;
import java.util.GregorianCalendar;
import android.app.Activity;
import android.content.Context;
import android.content.DialogInterface;
import android.content.Intent;
import android.content.SharedPreferences;
import android.content.SharedPreferences.Editor;
import android.net.Uri;
import android.os.Bundle;
import android.os.Environment;
import android.preference.PreferenceManager;
import android.view.View;
import android.view.View.OnClickListener;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.widget.CalendarView;
import android.widget.CalendarView.OnDateChangeListener;
import android.widget.Toast;

@SuppressWarnings("unused")
public class CalendarViewJan extends Activity {
	long date;
	CalendarView calendarView;
	GregorianCalendar c = new GregorianCalendar();

	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_calendar_view_jan);
		calendarView = (CalendarView) findViewById(R.id.calendarView1);
		calendarView.setOnDateChangeListener(new OnDateChangeListener() {
			@Override
			public void onSelectedDayChange(CalendarView view, int year,
					int month, int dayOfMonth) {

				if (calendarView.getDate() != date) {// in order for scroll to//
														// NOT behave like click
					date = calendarView.getDate();
					Toast.makeText(getApplicationContext(), "" + dayOfMonth, 0)
							.show();
					startActivity(new Intent("com.toe.checity.ReadJan"));
				}
			}
		});

	}
}
