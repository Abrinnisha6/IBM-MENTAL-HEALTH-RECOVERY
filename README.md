# IBM-MENTAL-HEALTH-RECOVERY
## TEAM : HACK CODE (SAV53)

## AIM :
 
 The Mental Health Recovery Project aims to support individuals on their journey toward mental well-being by providing a comprehensive and compassionate approach to recovery.


## MONITOR :

1.  A person's emotional, psychological, and social well-being.
2.  A journey of healing and growth, aiming to improve quality of life and reduce symptoms of mental illness.
3.  Negative attitudes, beliefs, and behaviors towards individuals with mental health conditions.
4. The ability to bounce back from adversity and challenges.


## CODE :

```python

import pandas as pd


file_path = 'mood_tracking_dataset_updated.csv.csv'
df = pd.read_csv(file_path)


df.head()


def analyze_mood():
    """Analyzes the user's mood based on their social activity, heartbeat, and sleep hours."""
    print("Analyzing Mood Based on Activity Metrics...\n")
    mood_summary = df.groupby('mood').mean()[['social_posts', 'heartbeat', 'sleep_hours', 'sentiment']]
    print(mood_summary)
    

analyze_mood()


psychologists_data = {
    "psychologist_id": [101, 102, 103],
    "name": ["Dr. Smith", "Dr. Johnson", "Dr. Lee"],
    "license_number": ["A12345", "B67890", "C54321"],
    "specialty": ["Anxiety", "Depression", "Trauma"],
    "availability": ["Monday, Wednesday", "Tuesday, Thursday", "Friday"],
    "email": ["drsmith@clinic.com", "drjohnson@clinic.com", "drlee@clinic.com"]
}


psychologists_df = pd.DataFrame(psychologists_data)

#
def match_psychologist_by_mood(mood):
    """Matches users with psychologists based on their mood."""
   
    mood_specialties = {
        "Happy": "General Well-being",
        "Stressed": "Anxiety",
        "Sad": "Depression",
        "Neutral": "General Well-being"
    }
    
    specialty_needed = mood_specialties.get(mood, "General Well-being")
    
 
    matching_psychologists = psychologists_df[psychologists_df['specialty'] == specialty_needed]
    
    if matching_psychologists.empty:
        print(f"No psychologists available for {mood} mood category.")
    else:
        print(f"Matching Psychologists for mood '{mood}':")
        print(matching_psychologists[['name', 'specialty', 'availability', 'email']])

match_psychologist_by_mood("Stressed")


def recommend_activity(heartbeat, sentiment, sleep_hours):
    """Recommends activities based on user metrics like heartbeat, sentiment, and sleep hours."""
    if heartbeat > 90 or sentiment < 0:
        print("Recommendation: You may be feeling stressed. Try meditation or consult a psychologist.")
    elif sleep_hours < 6:
        print("Recommendation: You may be sleep-deprived. Try improving your sleep routine.")
    else:
        print("Recommendation: You're doing well! Continue with activities like yoga or a light jog.")
        

recommend_activity(heartbeat=95, sentiment=-0.2, sleep_hours=5)


def book_appointment(user_id, psychologist_id):
    """Allows users to book appointments with psychologists."""
    psychologist = psychologists_df[psychologists_df['psychologist_id'] == psychologist_id].iloc[0]
    print(f"\nAppointment booked with {psychologist['name']}")
    print(f"Specialty: {psychologist['specialty']}")
    print(f"Contact: {psychologist['email']}")


book_appointment(user_id=1, psychologist_id=102)

print(" SAV53")
```


## OUTPUT :

![image](https://github.com/user-attachments/assets/50b5cd42-7ef4-4bd4-bc56-4cb438c2ec65)


## RESULT :

Mental health recovery is a personal journey that involves improving quality of life and reducing the impact of mental health challenges. It's a process that varies from person to person, and there's no one-size-fits-all approach.

