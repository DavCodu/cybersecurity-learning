# Network Diagnostics Toolkit

## Цел
Да науча какво са Ping, traceroute  и локална мрежа + python код .

## Команди които използвах
ping
tracert 

## Пример
ping google.com
tracert

## Какво научих
Ping е мрежова команда, която проверява дали друго устройство в мрежата отговаря.
Работи като изпраща малки пакети данни към даден адрес (IP или сайт) и чака отговор.
Показва дали връзката съществува , колко време (ms) отнема отговорът или дали има загуба на пакети

Traceroute показва през кои устройства (рутери) минава връзката, докато стигне до даден сайт или компютър.
Използва се за откриване къде точно има проблем в мрежата или виждане на пътя на интернет трафика
Local Area Network (LAN) е мрежа от устройства в малка област – например дом , училище ,офис или компютърна зала
В нея устройствата са свързани чрез Router , Switch или Wi-Fi
Примери за устройства в локална мрежа са компютри, телефони, принтери или сървъри


##Python код
Ping скрипт(проверява дали хост е онлайн):

import os

def ping_host(host):
    response = os.system(f"ping -c 4 {host}")
    
    if response == 0:
        print(f"{host} is online")
    else:
        print(f"{host} is unreachable")

Traceroute скрипт(показва пътя до traceroute):

import os

def traceroute(host):
    os.system(f"traceroute {host}")

LAN scanner(може да сканира устройства в локалната мрежа):

import subprocess

def scan_network():
    base_ip = "192.168.1."
    
    for i in range(1, 255):
        ip = base_ip + str(i)
        result = subprocess.run(["ping", "-c", "1", ip], capture_output=True)

        if "1 received" in result.stdout.decode():
            print(f"Active device: {ip}")

Главен файл:

from ping_tool import ping_host
from traceroute_tool import traceroute
from lan_scanner import scan_network

print("1. Ping host")
print("2. Traceroute")
print("3. Scan LAN")

choice = input("Choose option: ")

if choice == "1":
    host = input("Enter host: ")
    ping_host(host)

elif choice == "2":
    host = input("Enter host: ")
    traceroute(host)

elif choice == "3":
    scan_network()
