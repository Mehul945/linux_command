# linux_command
import subprocess
import os

while 1:
        a=input("\n"+os.getcwd()+" $ ")
        if a[0:2]=="cd":
                try:
                        os.chdir(a[3:])
                except Exception  as e:
                        print(a[3:]+" > >Is not valid path")
        if a=="ls":
                x=os.listdir()
                for i in x:
                        print(i)
        if a=="ls -a":
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe dir',shell=True)
        if a=="clear":
                os.system('cls')
        try:
                if a[:6]=='mkdir':
                        os.mkdir(a[5:])
        except Exception as e:
                pass

        try:
                if a[:2]=='rm':
                        os.remove(a[3:])
        except Exception as e:
                print("file dose'nt remove")

        if a[:5]=="touch":
                try:
                        #with open(a[6:],'w') as f:
                        subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe notepad '+a[6:],shell=True)
                                #text=input()
                                #f.write(text)
                except  Exception as e:
                        print("give valide name")
        if  a[0].isdigit():
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe '+a,shell=True)
        if a=='date':
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe '+a,shell=True)

        if a=='wifi':
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe netsh',shell=True)
        if a=='ifconfig':
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe ipconfig',shell=True)
        if a=='sysinfo':
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe systeminfo',shell=True)
        if a[:6]=='python' and '.py' in a:
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe python '+a[7:],shell=True)

        if a[:3]=='gcc' and '.c' in a:
                print(a[4:])
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe gcc '+a[4:],shell=True)
                print("Compilation succsess")
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe .\\a',shell=True)
        if a[:2]=='cp':
                o=a.index('*')
                print(a[3:(o)]+' '+a[o+1:])
        if a[:2]=='mv':
                o=a.index('*')
                subprocess.call('C:\Windows\system32\WindowsPowerShell\\v1.0\\powershell.exe Move-Item '+a[3:o]+' '+a[o+1:],shell=True)
