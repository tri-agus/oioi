# oioi

import pyttsx3
import pdfplumber
import PyPDF2

file = 'Panduan-KMLI-2019.pdf'

pdfFileObj = open(file,'rb')

pdfReader = PyPDF2.PdfFileReader(pdfFileObj)

pages = pdfReader.numPages

with pdfplumber.open(file) as pdf:
    for i in range(0,pages):
        page = pdf.pages[i]
        text = page.extract_text()
        print(text)
        speaker = pyttsx3. init()
        speaker.say(text)
        speaker.runAndWait()
    





#tgs



