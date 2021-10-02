# speech to text 


Exemple 


try:
     
    chunk_name = "Chunks/chunk_{}.wav".format(chunk_no)
    wf = wave.open(chunk_name, 'wb')
    wf.setnchannels(1)
    wf.setsampwidth(p.get_sample_size(pyaudio.paInt16))
    wf.setframerate(rate)
    wf.writeframes(b''.join(fr))
    wf.close()
    
    
    with sr.AudioFile(chunk_name) as source:
        audio = r.listen(source)
        text = r.recognize_google(audio)
        print(text)
        
except Exception as e:
    print("No Audio Detected",e)
