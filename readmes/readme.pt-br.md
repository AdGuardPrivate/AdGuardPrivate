# AdGuardPrivate

AdGuardPrivate é um fork do _AdGuardHome_, projetado para fornecer uma versão hospedada em SaaS com recursos aprimorados e personalização. Está hospedado em [AdGuard Private](https://adguardprivate.com).

## Principais Recursos

### Recursos Originais

1. **Bloqueio de Anúncios em Toda a Rede**

   - Bloqueia anúncios e rastreadores em todos os dispositivos da sua rede.
   - Opera como um servidor DNS que redireciona domínios de rastreamento para um "buraco negro".

2. **Regras de Filtragem Personalizadas**

   - Adicione suas próprias regras de filtragem personalizadas.
   - Monitore e controle a atividade da rede.

3. **Suporte a DNS Criptografado**

   - Suporta DNS-over-HTTPS, DNS-over-TLS e DNSCrypt.

4. **Servidor DHCP Integrado**

   - Fornece funcionalidade de servidor DHCP pronta para uso.

5. **Configuração por Cliente**

   - Configure as configurações para dispositivos individuais.

6. **Controle Parental**

   - Bloqueia domínios para adultos e impõe a Pesquisa Segura em motores de busca.

7. **Compatibilidade entre Plataformas**

   - Funciona em Linux, macOS, Windows e mais.

8. **Focado em Privacidade**
   - Não coleta estatísticas de uso ou envia dados, a menos que configurado explicitamente.

### Novos Recursos pelo AdGuardPrivate

1. **Roteamento DNS com Listas de Regras**

   - Personalize o roteamento DNS usando listas de regras definidas no arquivo de configuração.
   - Suporta regras de terceiros como [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat).

2. **Listas de Regras de Bloqueio Específicas para Aplicativos**

   - Configure o bloqueio de fontes de aplicativos específicos.
   - Suporta configurações de terceiros para gerenciamento flexível.

3. **DNS Dinâmico (DDNS)**

   - Fornece capacidades de resolução de nome de domínio dinâmico para vários cenários.

4. **Limitação de Taxa Avançada**

   - Implementa medidas eficientes de gerenciamento e controle de tráfego.

5. **Recursos de Implantação Aprimorados**
   - Suporte a balanceamento de carga.
   - Manutenção automática de certificados.
   - Conexões de rede otimizadas.

Para documentação detalhada, visite: [Documentação do AdGuardPrivate](https://adguardprivate.com/docs/)

## Como Usar

### Baixar o Binário

Você pode baixar o binário diretamente da página de [Releases](https://github.com/AdGuardPrivate/AdGuardPrivate/releases). Após o download, siga estes passos para executá-lo:

```bash
./AdGuardPrivate -c ./AdGuardHome.yaml -w ./data --web-addr 0.0.0.0:34020 --local-frontend --no-check-update --verbose
```

### Usar Imagem Docker

Alternativamente, você pode usar a imagem Docker disponível no [Docker Hub](https://hub.docker.com/repository/docker/adguardprivate/adguardprivate):

```bash
docker run --rm --name AdGuardPrivate -p 34020:80 -v ./data/container/work:/opt/adguardhome/work -v ./data/container/conf:/opt/adguardhome/conf adguardprivate/adguardprivate:latest
```