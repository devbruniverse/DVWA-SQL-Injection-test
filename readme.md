# Relatório: Teste de SQL Injection — DVWA

> **Aviso legal:** Todos os testes descritos aqui foram realizados em ambiente controlado (VMs). Não execute quaisquer técnicas deste repositório contra sistemas de terceiros sem autorização expressa.

## Sumário executivo
**Objetivo:** Avaliar comportamento da página de SQL Injection do DVWA para fins pedagógicos, documentar observações e propor mitigação.  
**Escopo:** Instância local do DVWA rodando em VM Metasploitable, nível DVWA: low.  

## Ambiente de teste
- Kali  
- DVWA  
- Snapshot Antes: sim  
- Rede: Host-only/Internal

## Metodologia (resumo)
- Inspeção manual de formulários e requisições sqlmap para identificar possíveis vulnerabilidades a SQL Injection.  

## Evidências
As evidências estão em `evidence/`.  
**Atenção:** apenas arquivos sanitizados foram comitados.

## Observações e achados
- É possível obter a lista completa de usuários através de uma injeção de sql no campo ID
- Parâmetro sensível identificado: `id` — observação: necessário parametrizar a query.
- Mensagens de erro de DB observadas: não.  
- Encriptação de senhas fraca.

## Mitigações recomendadas
1. Use *prepared statements* / query parameterization.  
2. Validação por whitelist e limite de tamanho de input.  
3. Conta da aplicação com privilégios mínimos no DB.  
5. WAF como camada adicional.

## Checklist de entrega
- [ x] Evidências sanitizadas em `evidence/`  

## Apêndice
- Prints e logs: veja `evidence/`.  
- Notas de laboratório: `notes/lab-plan.md`

