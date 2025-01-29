# apna.ai
He is a virtual assistance
import speech_recognition as sr
import webbrowser
import pyttsx3
from openai import OpenAI
import requests


recognzer = sr.Recognizer()
engine = pyttsx3.init()
def speak(text):
    engine.say(text)
    engine.runAndWait()


def processComand(c):
    if "open google" in c.lower():
        webbrowser.open("https://google.com")
    elif "open youtub" in c.lower():
        webbrowser.open("https://www.youtube.com/") 
    elif"open facebook" in c.lower():
        webbrowser.open("https://facebook.com") 
    elif"open linkedin" in c.lower():
        webbrowser.open("https://linkedin.com")  
    elif c.lower().startswith("play"):
         song = c.lower().split("  ")[1]   
         
         

        
if __name__=="__main__":
    speak("initializing   Aman .... " )
    while True:
        #lesten for the wake word " Alina"
        # optain from the microphone
        r = sr.Recognizer() 
        print("recognizing...")
        try:
            with sr.Microphone() as source:
                print('listening...')
                audio = r.listen(source,timeout=2,phrase_time_limit=1) 
            
            command = r. recognize_google(audio) 
            if(command=="Aman "):
                speak("ready for comand")
                with sr.Microphone() as source:
                    print("Aman Active....")
                    audio = r.listen(source)
                    command = r. recognize_google(audio)

                    processComand(command) 
                
                
        except Exception as e:
            print("Error; {0}".format(e)) 
