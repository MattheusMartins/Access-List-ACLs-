# Access-List-ACLs-

Tarefas:

Configure as ACLs da seguinte maneira (dicas abaixo):
1) Restrinja o tráfego internamente da seguinte forma:
- Use a lista de acesso número 100
- Dentro do PC 1 na sub-rede 10.1.2.0/24 só pode acessar os servidores HTTP 1 e 2 na sub-rede 10.1.1.0/24 usando HTTP e HTTPS (use apenas duas linhas em sua ACL para fazer isso).
- Nenhum outro PC ou servidor na sub-rede 10.1.2.0/24 pode acessar a sub-rede 10.1.1.0/24 (Adicionar explicitamente esta linha. Isso normalmente é feito para registrar o tráfego com a palavra log, mas PT não suporta registro)
- Hosts na sub-rede 10.1.2.0/24 podem acessar qualquer outra rede
- Vincule a lista de acesso no local mais eficiente no Roteador1

2) Restrinja o tráfego externamente da seguinte forma:
- Use a lista de acesso número 101
- Qualquer dispositivo externo pode acessar servidores HTTP internos usando HTTP ou HTTPS
- Nenhum dispositivo externo pode acessar a sub-rede do usuário 10.1.2.0/24 (Adicione explicitamente esta linha. Isso normalmente é feito para registrar o tráfego com a palavra log, mas PT não suporta registro)
- Vincule a lista de acesso no local mais eficiente no Roteador1

3) Verificação:
- Verifique se o Inside PC1 pode acessar os servidores HTTP internos 1 e 2, mas não outros servidores HTTP (servidor 3 e 4)
- Verifique se o Inside PC2 não pode acessar os servidores HTTP internos
- Verifique se dentro do PC1 e do PC2 podem navegar para cisco.com e facebook.com
- Verifique se PC1 externo pode acessar ambos os servidores internos usando HTTP (servidor 1) e HTTPS (servidor), mas não pode executar ping nos PCs internos
 
Dicas:
1) Pense em como o binário funciona
2) Pense no tráfego DNS
3) Pense no tráfego de retorno dos servidores da Internet

<img src="https://raw.githubusercontent.com/MattheusMartins/Access-List-ACLs-/main/1.PNG">
