import easyocr
from pathlib import Path
reader = easyocr.Reader(['ch_sim','en']) # this needs to run only once to load the model into memory

### jpg转png

#importing required packages and library
import cv2
  
def jpg2png(path,i):
    # Loading .png image
    png_img = cv2.imread(path)
    # converting to jpg file
    #saving the jpg file
    print(path+'.jpg')
    cv2.imwrite(path+'.jpg', png_img, [int(cv2.IMWRITE_JPEG_QUALITY), 100])


import numpy as np
import cv2 as cv
def gif2jpg(path,i):
    gif = cv.VideoCapture(path)
    ret, frame = gif.read()
    cv.imwrite(path+'.jpg', frame)


import os
from PIL import Image
import matplotlib.pyplot as plt

#读取images文件夹下所有文件的名字
imagelist = [f for f in os.listdir('/mnt/fengzeng/data/fzdata/image/ctg/') if f.endswith('.png')]  # 获取所有txt文件的名称
print(imagelist)
rootdir="/mnt/fengzeng/data/fzdata/image/ctg/"

for i in range(len(imagelist)):
    gif2jpg(rootdir+imagelist[i],i)
    os.remove(rootdir+imagelist[i])

#print(rootdir+imagelist[0])
#for i in range(len(imagelist)):
    #img = Image.open(rootdir+imagelist[i])
#读取images文件夹下所有文件的名字
imagelist = [f for f in os.listdir('/mnt/fengzeng/data/fzdata/image/ctg/') if f.endswith('.jpg')]  # 获取所有txt文件的名称
#print(imagelist)
rootdir="/mnt/fengzeng/data/fzdata/image/ctg/"
def readerpic(rootdir,imagelist):
    for i in range(len(imagelist)):
        print(rootdir+imagelist[0])
        img = Image.open(rootdir+imagelist[i])
        result = reader.readtext(img)
        print(rootdir+imagelist[i])
        img.close()
        os.remove(rootdir+imagelist[i])
        for i in result:
            word = i[1]
            print(word)
            savetxt(word,rootdir)
def savetxt(contents,path):
    #if not os.path.exists(path+".txt"):
        #print(path)
        with open(path+"pic2txt.txt",'a') as f:
            #f.write(path)
            f.write(contents+"\n")        
        f.close()
    #else:
        #print("Files already exists!")
        
readerpic(rootdir,imagelist)  
