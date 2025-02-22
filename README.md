import requests 
import os
import json

logo = """
███╗   ██╗██████╗ ██████╗     ████████╗ ██████╗  ██████╗ ██╗     
████╗  ██║██╔══██╗██╔══██╗    ╚══██╔══╝██╔═══██╗██╔═══██╗██║     
██╔██╗ ██║██████╔╝██║  ██║       ██║   ██║   ██║██║   ██║██║     
██║╚██╗██║██╔══██╗██║  ██║       ██║   ██║   ██║██║   ██║██║     
██║ ╚████║██║  ██║██████╔╝       ██║   ╚██████╔╝╚██████╔╝███████╗
╚═╝  ╚═══╝╚═╝  ╚═╝╚═════╝        ╚═╝    ╚═════╝  ╚═════╝ ╚══════

"""


while True:
    os.system("title NRD TOOL")
    os.system("cls")
    print(logo)
    print("SC TOOL")
    print("[1] Ip Lookup")
    print("[2]Webhook Sender")
    print("[3]Show HWID")
    print("")
    x - input("Option: ")

    if x == "1":
        os.system("cls")
        print("IP LOOKUP\n")
        ip = input("Entre IP: ")

        r = requests.get(f"https://ip-api.com/json/{ip}")
        data = r.json()
        print("RESULTS\n")
        print(f"Country: "{data["Country"]})
        print(f"City: {data["City"]}")
        print(f"Regon: {data["regionName"]}")
        print(f"TimeZone: {data["timezone"]}")
        print("")
        pause = input("Press enter to return...") 


    if x == '2':
        os.system("cls") 
        print("WHEBHOOK SENDER\n")
        url = input("webhook URL: ")
        message = input("Webhook URL: ")
        name = input ("Webhook URL : ")
        
        data = {
            "content": message,
            "username": name
        }


        try:
            r = requests.post(url, json=data)
        except:
            print("Webhook Sent!")
        except:
            print("ERROR SENDING WEBHOOK")

        print() 
        pause = input("Press enter to return...") 
