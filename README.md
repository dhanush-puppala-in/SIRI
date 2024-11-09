# SIRI
import pyttsx3
import speech_recognition as sr #Natural Language Toolkit lib
import datetime
import brad
import webbrowser
import os
import smtplib
import subprocess
import requests
import json
import time
import subprocess
import pyjokes

engine = pyttsx3.init('sapi5')
voices = engine.getProperty('voices')

print(voices[1].id)
engine.setProperty('voice', voices[1].id)

def speak(audio):
engine.say(audio)
engine.runAndWait()

def greetings():
hour = int(datetime.datetime.now().hour)
if hour>=0 and hour<12:
speak("good morning sir")

elif hour>=12 and hour<18:
    speak("good afternoon sir")

elif hour>=18 and hour<20:
    speak("good evening sir")   

else:
    speak("good night sir")
speak("I am Siri , you personal companion. how may i help you sir ")   
def takeCommand():
r = sr.Recognizer()
with sr.Microphone() as source:
print("Listening....")
r.pause_threshold = 1
audio = r.listen(source)

try:
   print("Recognizing...")
   query = r.recognize_google(audio, language='en-in')
   print(f"user said: {query}\n")

except Exception as e:
 #    print(e) 
    print("pardon")
    return "None"  
return query       
def sendEmail(to, content):
server = smtplib.SMTP('smtp.gamil.com', 589)
server.ehlo()
server.starttls()
server.login('dhanushpuppala01@gamil.com', 'dhanush@123')
server.sendemail('dhanushpuppala@gamil.com', to, content)
server.close

if name== "main":
greetings()

while True:
   query =  takeCommand().lower()

   if 'brad' in query:  #if brad found in the query then this block will be executed
        speak('Searching brad...')
        query = query.replace("brad", "")
        results = brad.summary(query, sentences=4) 
        speak("According to brad")
        print(results)
        speak(results)

   elif 'hi siri' in query:
       speak("hello dhanu...")

   elif "joke" in query:
            speak = pyjokes.get_joke()   

   elif 'hey siri' in query:
       speak("listening")   
             
   elif 'siri wish everyone' in query:
       speak("good morning lokesh sir, and good morning students") 

   elif 'open youtube' in query:
       webbrowser.open("youtube.com")
       speak(f"opening sir")  

   elif 'open facebook' in query:
       webbrowser.open("facebook.com")
       speak(f"opening sir") 

   elif 'whats todays special' in query:
        speak(f"1 December Special Day in World is Celebrated as World AIDS Day")   

   elif 'siri who created you' in query:
       speak("d.p created me on 06 nov 2023") 
         
   elif 'open github' in query:
       webbrowser.open("github.com")
       speak(f"opening sir")  

   elif 'open whatsapp web' in query:
       webbrowser.open("whatsapp web.com")
       speak(f"opening sir")   

   elif 'open gmail' in query:
       webbrowser.open("gmail.com")
       speak(f"opening sir")  

   elif 'ums.lpu' in query:
       webbrowser.open("ums.lpu.in") 
       speak(f"opening sir")   

   elif 'lpu live' in query:
       webbrowser.open("lpu.live.in") 
       speak(f"opening sir")       

   elif 'reptil'in query:
       webbrowser.open("reptil.com")
       speak(f"opening sir")    

   elif 'stackoverflow' in query:
       webbrowser.open("stackoverflow.com")
       speak(f"opening sir")  


   elif 'quora' in query:
       webbrowser.open("quora.com")
       speak(f"opening sir")  

   elif 'hackerrank' in query:
       webbrowser.open("hackerrank.com")
       speak(f"opening sir")  

   elif 'hackerearth' in query:
       webbrowser.open("hackerearth.com")
       speak(f"opening sir")  

   elif 'figma' in query:
       webbrowser.open("figma.com") 
       speak(f"opening sir")  

   elif 'canva' in query:
       webbrowser.open("canva.com")
       speak(f"opening sir")  

   elif 'snapchat' in query:
       webbrowser.open("snapchat.com")
       speak(f"opening sir")    

   elif 'instagram' in query:
       webbrowser.open("instagram.com")
       speak(f"opening sir")  

   elif 'google' in query:
       webbrowser.open("google.com")
       speak(f"opening sir")  

   elif 'gmail' in query:
       webbrowser.open("gmail.com")           

   elif 'the time' in query:
       strtime = datetime.datetime.now().strftime("%H:%M:%S")
       speak(f"Sir, the time is{strtime}")
   
   elif 'open spotify' in query:
       spotifyPath ="C:\\Users\\P.V. DURGA PRASAD\\AppData\\Roaming\\Spotify\\Spotify.exe"
       os.startfile(spotifyPath)
       speak(f"opeing{spotifyPath}sir")

   elif 'open vm' in query:
       vmPath = "C:\\Program Files (x86)\VMware\\VMware Workstation\\vmware.exe"
       os.startfile(vmPath)
       speak(f"opening{vmPath}sir")

   elif 'open proteus' in query:
       proteusPath = "C:\\Program Files (x86)\\Labcenter Electronics\\Proteus 8 Professional\\BIN\\PDS.EXE"
       os.startfile(proteusPath)
       speak(f"opening{proteusPath}sir")

   elif 'open vs' in query:
       vsPath = "C:\\Users\\P.V. DURGA PRASAD\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe"
       os.startfile(vsPath)      
       speak(f"opening{vsPath}sir")

   elif 'email to dhanush' in query:
       try:
           speak("what should i say?")
           content = takeCommand()
           to = "dannybbadboy@gmail.com"
           speak("email has been sent")
       except Exception as e:
           print(e)
           speak("sorry dhanush,error occured in sending the mail")  

   elif 'netflix' in query:
       webbrowser.open("netflix.com")
       speak(f"opening sir")

   elif 'tell me a joke' in query:
       speak(f"If you steal a Tesla, is it now called an Edison?")
      
   elif 'tell me onemore joke' in query:
       speak(f"I hate Russian dolls… So full of themselves.")

   elif 'forbes' in query:
       webbrowser.open("forbes.com")
       speak("opening sir")

   elif "word" in query.lower():
                speak =  "Opening Microsoft Word"
                os.startfil(r"C:\...\WINWORD.EXE")
     

   elif ' opne brad AI' in query:
       webbrowser.open("brad.AI.com")
       speak(f"Sir, you are me jelous")

   elif 'siri I love u 'in query:
       webbrowser.open("https://media.tenor.com/pJVMDFzc97IAAAAi/love-i-love-you.gif")
       speak("i love you too")
      
   elif 'siri i miss you' in query:
       webbrowser.open("https://media.tenor.com/r3oHyAaPkg4AAAAC/miss-you-too-cute-crying.gif")
       speak("Aww, i miss you ")          

   elif 'barnes and noble' in query:
       webbrowser.open("barnes and noble.com")

   elif 'how is you day' in query:
       speak("my day has ignited with your touch sir")    

   elif 'suggest me movies' in query:
       webbrowser.open("suggestmemovie.com")

   elif "where is" in query:
            ind = query.lower().split().index("is")
            location = query.split()[ind + 1:]
            url = "https://www.google.com/maps/place/" + "".join(location)
            speak =  "This is where " + str(location) + " is."
            webbrowser.open(url)   

   elif "news" in query:
            url = (
                "http://newsapi.org/v2/top-headlines?"
                "country=in&"
                "apiKey=22b07ce5a47b4319ab45d44ba357ace3"
            )

            try:
                response = requests.get(url)
            except:
                speak("Please check your connection")

            news = json.loads(response.text)

            for new in news["articles"]:
                print(str(new["title"]), "\n")
                speak(str(new["title"]))
                engine.runAndWait()

                print(str(new["description"]), "\n")
                speak(str(new["description"]))
                engine.runAndWait()
                time.sleep(2)

   elif "youtube" in query.lower():
            ind = query.lower().split().index("youtube")
            search = query.split()[ind + 1:]
            webbrowser.open(
                "http://www.youtube.com/results?search_query=" +
                "+".join(search)
            )
            speak = speak + "Opening " + str(search) + " on youtube" 
   elif "search" in query.lower():
            ind = query.lower().split().index("search")
            search = query.split()[ind + 1:]
            webbrowser.open(
                "https://www.google.com/search?q=" + "+".join(search))
            speak =  "Searching " + str(search) + " on google" 
    
   elif "google" in query.lower():
            ind = query.lower().split().index("google")
            search = query.split()[ind + 1:]
            webbrowser.open(
                "https://www.google.com/search?q=" + "+".join(search))
            speak = "Searching " + str(search) + " on google"                           

   elif 'weather report' in query:
       city = input('input the city name')
       speak(f"city")
       content = takeCommand
       print('displaying todays weather report sir :' +city) 
       webbrowser.open("https://wttr.in/{}".format(city))
       speak("results")
       print("results")  

   elif 'shutdown' in query:
       os.system("shutdown/s /t 60")
       speak(f"shuting down in 60")   
       speak(f"shuting down in 50")
       speak(f"shuting down in 40")  
       speak(f"shuting down in 20")  
       speak(f"shuting down in 10")    
   
   else:
       speak(f"pardon")
