# NIP.IO: Serviço de DNS curinga

**NIP.IO** é um serviço de DNS curinga (wildcard DNS) que permite mapear qualquer endereço IP para um nome de host de forma simples e rápida. Sua principal função é eliminar a necessidade de editar manualmente o arquivo `/etc/hosts` para criar mapeamentos personalizados entre hostnames e endereços IP.

## Sobre

**NIP.IO** baseia-se no [PowerDNS](https://www.powerdns.com/) com um [PipeBackend](https://doc.powerdns.com/authoritative/backends/pipe.html) simples e customizado, escrito em Python: [`backend.py`](https://github.com/exentriquesolutions/nip.io/blob/master/nipio/backend.py)

É um projeto *open source* sob licença *Apache 2.0*.

## Principais características do NIP.IO

- **Mapeamento automático:** O serviço mapeia automaticamente qualquer endereço IP para um hostname usando formatos específicos.
- **Flexibilidade de notação:** Suporta três tipos de notação para representar endereços IP:
  - **Notação de ponto:** `10.0.0.1.nip.io` (host `10.0.0.1`), `10.15.18.44.nip.io` (host `10.15.18.44`);
  - **Notação de traço:** `10-0-0-1.nip.io` (host `10.0.0.1`), `10-15-18-44.nip.io` (host `10.15.18.44`);
  - **Notação hexadecimal:** `0a000001.nip.io` (host `10.0.0.1`), `0a0f122c.nip.io` (host `10.15.18.44`).
- **Suporte a subdomínios:** Permite adicionar nomes personalizados antes do endereço IP, como `app.10.8.0.1.nip.io` (`app.0a080001.nip.io`) ou `subdom1.subdom2.10-15-18-44.nip.io` (`subdom1.subdom2.0a0f122c.nip.io`).
- **Compatibilidade com serviços de certificados:** As notações de traço e hexadecimal são especialmente úteis para serviços como Let's Encrypt, pois são tratadas como subdomínios regulares.

## Usos comuns

- **Desenvolvimento local:** Facilita o teste de aplicações web em ambientes de desenvolvimento local sem a necessidade de configurar DNS.
- **Hospedagem temporária:** Permite acessar servidores web temporários usando nomes de domínio, mesmo sem um DNS configurado ou configuração no arquivo `/etc/hosts`.
- **Configuração rápida de SSL/TLS:** Possibilita a obtenção de certificados SSL/TLS para servidores em VPS ou conexões domésticas sem configuração complexa de DNS.

## Concluindo

É importante notar que, embora o NIP.IO seja um serviço gratuito e de código aberto, existem alternativas similares como:

- `traefik.me`
- `sslip.io`
- `local.gd` (IP é mapeado para o `localhost`/`127.0.0.1`).

Além disso, é preciso considerar que, como qualquer serviço externo, há o risco de interrupção. É recomendável ter um plano de contingência para casos críticos.
