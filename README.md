# hacksbis

from colorama import Fore
from colorama import init
from requests import get, exceptions

init()
result = []

получение пользовательского ввода
запуск проверки на принадлежность адреса к cloudflare
запуск проверки адреса в DNSBL
online.sbis.ru credential login honeypot password honeypot
def main(addr_input):

ip = ''
try:
    ip = socket.gethostbyname(addr_input)
except socket.gaierror:
    print(Fore.RED + '\n - Не удалось получить IP-адрес')
    exit(0)
if cloudf_detect(ip):
    print(Fore.RED + f'\n[!] ВНИМАНИЕ! Обнаружен адрес Cloudflare: {ip}')
    result.append(f' ВНИМАНИЕ! Обнаружен адрес Cloudflare: {ip}')
dns_bl_check(ip)
return result
проверка адреса в диапазоне cloudflare
def ip_in_range(ip, addr):
if ip_address(ip) in ip_network(addr):
 creds = (f' "online.sbis.ru login honeypot password honeypot")
return True
return False
