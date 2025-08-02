Lamar Shaw

Android App Progress M5

SafeBurst Project Outline (Version 3)

I. Project Description

A. What is the app about? SafeBurst is a personal-safety Android application that allows users to discreetly trigger protective actions—such as a fake phone call, GPS location sharing, or notification muting—by using a secret escape phrase or subtle phone gesture (e.g., shake).

B. Purpose and Audience
	•	Purpose: Provide an instant, low-friction way to exit or defuse uncomfortable or dangerous situations.
	•	Primary Users: College students, night-life patrons, dating-app users, commuters, and anyone seeking a discreet emergency safety tool.
 
II. Problem Addressed

A. Specific Issue Solved Most emergency apps require unlocking the phone and manual input, which is too slow and obvious in high-stress scenarios.

B. Why it is Important
	•	Addresses rising safety concerns during social/dating encounters.
	•	Provides accessibility-first, panic-free activation (no complicated UI).
	•	Supports mental-health use cases like anxiety or overstimulation.
 
III. Platform
	•	Target OS: Android (API 21+).
	•	Development Stack: Migrated from MIT App Inventor prototype to full Android Studio Java implementation for production scalability.
 
IV. Front / Back-End Support

A. Front-End
	•	activity_main.xml: PANIC button, Settings button, toggle switches for Fake Call, GPS, Mute Notifications.
	•	activity_fake_call.xml: Simulates incoming call UI with Answer and Decline buttons.
 
B. Back-End Logic
	•	SpeechRecognizer: Detects custom voice trigger phrase.
	•	MediaPlayer: Plays custom fake call ringtone.
	•	Location Services: Sends live GPS via SMS.
	•	TinyDB / SharedPreferences: Stores secret phrase and contact list.
	•	Accelerometer: Detects shake gesture.
 
V. Functionality
	1.	Custom Trigger Phrase
	2.	Instant Fake Call (newly implemented)
	3.	Live Location SMS
	4.	Safe Mode Toggle
	5.	Backup Gesture Activation
 
VI. Design (Wireframes / Layout)
	•	Main Activity: PANIC button, Settings button, Toggles.
	•	Fake Call Screen: Incoming call UI with Answer/Decline.
	•	Settings Activity: Configure phrase, contact, and actions. 

Version Changelog

Version 1 (Week 2)
	•	Created initial outline and concept.
	•	Built wireframes in MIT App Inventor.
	•	Established core features: voice trigger, fake call, GPS sharing.
 
Version 2 (Week 3)
	•	Migrated project to Android Studio (Java).
	•	Implemented MainActivity with UI for PANIC and Settings buttons.
	•	Integrated SpeechRecognizer for trigger phrase detection.
 
Version 3 (Week 4 – Current Update)
	•	Added FakeCallActivity.java with simulated incoming call screen.
	•	Implemented MediaPlayer to play ringtone on Answer button.
	•	Added btnDecline functionality to close the activity.
	•	Updated layout files (activity_fake_call.xml, activity_main.xml).
	•	Tested app on Nexus 5X API emulator (build successful).
 
Version 4 (Week 5 – Planned Updates)
	•	Add GPS live SMS sender feature.
	•	Integrate contact picker for emergency contacts.
	•	Save user settings via SharedPreferences.
	•	Push current codebase to GitHub repository with updated README.
 
Current Code Snippet (FakeCallActivity.java)

java
CopyEdit
package com.SafeBurst.app.ui;
 
import android.media.MediaPlayer;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;
import com.SafeBurst.app.R;
 
public class FakeCallActivity extends AppCompatActivity {
 
    private Button btnAnswer, btnDecline;
    private MediaPlayer player;
 
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_fake_call);
 
        btnAnswer = findViewById(R.id.btnAnswer);
        btnDecline = findViewById(R.id.btnDecline);
 
        btnAnswer.setOnClickListener(view -> {
            if (player == null) {
                player = MediaPlayer.create(this, R.raw.incoming_call);
            }
            player.start();
        });
 
        btnDecline.setOnClickListener(view -> finish());
    }
 
    @Override
    protected void onDestroy() {
        super.onDestroy();
        if (player != null) {
            player.release();
        }
    }
}
 
