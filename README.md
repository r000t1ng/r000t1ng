<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg?v=13">
  <source media="(prefers-color-scheme: light)" srcset="assets/banner-light.svg?v=13">
  <img src="assets/banner-dark.svg?v=13" alt="Ricardo Martins, security researcher">
</picture>

## Research

| Disclosure | Finding | Reference |
| :--- | :--- | :--- |
| **Systemic vulnerability**<br>NF‑e | Brazil's electronic invoice sits under every commercial transaction in the country, and issuing one is a legal requirement, so nothing about the exposure is opt in. The access key carries sequential fields and the validation service has no rate limit, so valid keys can be brute forced and every hit returns another company's complete invoice. This is the machinery behind the fake boleto fraud: real CNPJ, real amounts, attacker's barcode. | [Writeup](https://pt.linkedin.com/pulse/voc%C3%AA-conhece-o-novo-golpe-do-boleto-falso-ricardo-martins)<br>[LASDiGov 2025](https://sol.sbc.org.br/index.php/wcge/article/view/36315) |
| **Remote code execution**<br>WhatsApp Desktop | A `.pyz` attachment executes the moment it is opened from the chat, on the Windows client of a platform with two billion users. Defender, UAC and antivirus each decline to act for their own reason, and a guest account escalates to administrator on the way. Every machine running the client was one attachment away from full compromise, with no prompt anywhere in the chain. | [PoC](https://github.com/r000t1ng/Reverse-Shell-Whatsapp) |
| **Systemic vulnerability**<br>Web browsers | A `history.pushState` flood carrying a URL that grows on every call. The renderer runs out of memory and the session history is buried. Filed as a zero day and closed as working as intended, because no single API call does anything it is not allowed to do. The bug is the absence of a ceiling, which is exactly why it took time to land. | [PoC](https://github.com/r000t1ng/Crash4Browser) |
| **Systemic vulnerability**<br>Web browsers | Unbounded IndexedDB writes in a loop that never yields, so the browser never applies backpressure, and the origin's storage quota stays consumed after the tab is closed. Same reception as the one above, rejected first and recognised later, for the same reason. Neither is memory corruption, so neither fit the shape vendors were looking for. | [PoC](https://github.com/r000t1ng/Overflow-by-IndexedDB) |
| **HTML injection**<br>LinkedIn notifications | HTML injection in the notification pipeline. Phishing delivered from `notifications@linkedin.com` with attacker controlled subject, body and redirect. No access to the victim's mailbox required. | [The Hack](https://www.thehack.com.br/exclusivo-falha-grave-no-linkedin-permite-envio-de-phishing-pelo-email-oficial-da-empresa/) |
| **Denial of service**<br>LinkedIn | Direct messages and chat are unintegrated services, so each scripted message spawns its own window. Any connection can be buried under thousands of them until the browser gives out. | [The Hack](https://www.thehack.com.br/exclusivo-pesquisadores-descobrem-falha-que-permite-envio-de-spam-em-massa-no-linkedin/) |
| **HTML injection**<br>LinkedIn | A separate injection, disclosed through HackerOne and awarded a bounty. | [HackerOne](https://hackerone.com/r00t1ng) |
| **Host manipulation**<br>Broadcom SiteMinder | `TARGET` accepts an arbitrary host, writes it into a hidden field, and uses it as the post authentication redirect. Real domain, real login, real credentials, and the redirect only fires afterwards. | [PoC](https://github.com/r000t1ng/Host-Manipulation-Siteminder) |
| **Reflected XSS**<br>Loja Integrada | The filter runs before normalization, so the hyphens in `s-v-g` survive the check and are stripped only on the way to the DOM. Default address component, reached through `cep`. | [PoC](https://github.com/r000t1ng/loja-integrada-xss) |

## Recognition

| Organization | Form | Year |
| :--- | :--- | :--- |
| **Unilever** | Hall of fame | 2023, 2025, 2026 |
| **Deutsche Bank** | Bounty awarded | 2023, 2024, 2025 |
| **Linx** | Letter of appreciation | 2025 |
| **[United Nations](https://unite.un.org/en/ict-security/hall-fame)** | Hall of fame | 2024 |
| **[Motorola Solutions](https://www.motorolasolutions.com/en_us/about/security-vulnerability/hall-of-fame.html)** | Hall of fame | 2024 |
| **Dell** | Hall of fame | 2024 |
| **Harvard University** | Public disclosure | 2024 |
| **NASA** | Letter, Vulnerability Disclosure Policy | 2022, 2023 |
| **iFood** | Hall of fame | 2021, 2022, 2023 |
| **Mastercard** | Hall of fame | 2023 |
| **IBM** | Hall of fame | 2023 |
| **Nubank** | Bounty awarded | 2023 |
| **American Airlines** | Bounty awarded | 2023 |
| **HackerOne** | Bounty awarded | 2022 |
| **Riot Games** | Bounty awarded | 2022 |
| **Drexel University** | Letter, Office of the CISO | 2022 |
| **LinkedIn** | Bounty awarded | 2021 |
| **Uber** | Hall of fame | 2021 |
| **Receita Federal** | Public disclosure | 2020 |
| **Razer** | Public disclosure | 2020 |
| **Toyota** | Hall of fame | 2019 |
| **Telefônica Brazil** | Hall of fame | 2018 |
| **[Open Bug Bounty](https://www.openbugbounty.org/researchers/r00t1ng/)** | Outstanding Security Researcher | 2017 |

| Type | Detail |
| :--- | :--- |
| **Write up** | [Estadão](https://bluestudioexpress.estadao.com.br/conteudo/2024/05/20/evento-discute-acoes-para-combater-fraudes-em-boletos-no-b2b/) on the NF-e research into boleto fraud in B2B payments |
| **Open source** | Penetration testing on the [OWASP ModSecurity CRS](https://innovatorsforopensuse.org/2023/09/05/owasp-modsecurity-crs-for-everyone-on-opensuse/) packaging for openSUSE, verifying the Core Rule Set protections before release |

## Talks

| Year | Talk | Venue | Links |
| :--- | :--- | :--- | :--- |
| 2025 | Trusted Exploits: Scaling Attacks Through Trusted Surfaces and WAF Bypass | OWASP São Paulo | [Watch](https://www.youtube.com/watch?v=TFFCrLLabZQ) |
| 2024 | Boleto Fraud in B2B Payments | Simplifica+ Talks | [Watch](https://www.youtube.com/watch?v=kkH-MCX9GBs) |
| 2022 | Bug Bounty: A Journey Behind the Bug | OWASP São Paulo | [Watch](https://www.youtube.com/watch?v=QIsIGkduIBo) |
| 2019 | Defensive Security | Anhanguera Educacional, on campus | |
| 2019 | Offensive Security | Anhanguera Educacional, on campus | |
| 2017 | Google Hacking and SQL Injection: Finding Vulnerabilities Across the Web<br><sub>1,125 registered</sub> | 2nd RootDay Web Conference | [Event page](https://www.eventials.com/rootday/google-hacking-e-sql-injection-buscando-vulnerabilidades-pela-web/) |
| 2017 | Social Engineering and How It Is Used Today | 2nd RootDay Web Conference | |

All talks were delivered in Portuguese.

<details>
<summary><strong>&nbsp;🇧🇷&nbsp; Versão em português</strong></summary>

<br>

### Pesquisas

| Divulgação | Achado | Referência |
| :--- | :--- | :--- |
| **Vulnerabilidade sistêmica**<br>NF‑e | A nota fiscal eletrônica está embaixo de toda transação comercial do país, e emitir uma é exigência legal, então nada na exposição é opcional. A chave de acesso carrega campos sequenciais e o serviço de validação não tem rate limit, então chaves válidas podem ser obtidas por força bruta e cada acerto devolve a nota fiscal completa de outra empresa. É a engrenagem por trás da fraude do boleto falso: CNPJ real, valores reais, código de barras do atacante. | [Writeup](https://pt.linkedin.com/pulse/voc%C3%AA-conhece-o-novo-golpe-do-boleto-falso-ricardo-martins)<br>[LASDiGov 2025](https://sol.sbc.org.br/index.php/wcge/article/view/36315) |
| **Execução remota de código**<br>WhatsApp Desktop | Um anexo `.pyz` executa no instante em que é aberto pela conversa, no cliente Windows de uma plataforma com dois bilhões de usuários. Defender, UAC e antivírus se recusam a agir, cada um pelo seu motivo, e uma conta convidada sobe para administrador no caminho. Toda máquina rodando o cliente estava a um anexo de distância do comprometimento total, sem nenhum aviso em ponto algum da cadeia. | [PoC](https://github.com/r000t1ng/Reverse-Shell-Whatsapp) |
| **Vulnerabilidade sistêmica**<br>Navegadores web | Flood de `history.pushState` carregando uma URL que cresce a cada chamada. O renderizador fica sem memória e o histórico da sessão é soterrado. Registrado como zero day e fechado como comportamento esperado, porque nenhuma chamada de API isolada faz algo que não lhe seja permitido. O bug é a ausência de um teto, e é exatamente por isso que demorou a ser aceito. | [PoC](https://github.com/r000t1ng/Crash4Browser) |
| **Vulnerabilidade sistêmica**<br>Navegadores web | Gravações ilimitadas no IndexedDB num laço que nunca devolve o controle, então o navegador nunca aplica backpressure, e a cota de armazenamento da origem continua consumida depois que a aba fecha. Mesma recepção do anterior, rejeitado primeiro e reconhecido depois, pelo mesmo motivo. Nenhum dos dois é corrupção de memória, então nenhum tinha o formato que os fabricantes procuravam. | [PoC](https://github.com/r000t1ng/Overflow-by-IndexedDB) |
| **Injeção de HTML**<br>Notificações do LinkedIn | Injeção de HTML no pipeline de notificações. Phishing entregue a partir do `notifications@linkedin.com` com assunto, corpo e redirecionamento controlados pelo atacante. Sem precisar de acesso à caixa de entrada da vítima. | [The Hack](https://www.thehack.com.br/exclusivo-falha-grave-no-linkedin-permite-envio-de-phishing-pelo-email-oficial-da-empresa/) |
| **Negação de serviço**<br>LinkedIn | Mensagem direta e chat são serviços não integrados, então cada mensagem automatizada abre a própria janela. Qualquer contato pode ser soterrado debaixo de milhares delas até o navegador desistir. | [The Hack](https://www.thehack.com.br/exclusivo-pesquisadores-descobrem-falha-que-permite-envio-de-spam-em-massa-no-linkedin/) |
| **Injeção de HTML**<br>LinkedIn | Uma injeção distinta, divulgada pelo HackerOne e premiada com bounty. | [HackerOne](https://hackerone.com/r00t1ng) |
| **Manipulação de host**<br>Broadcom SiteMinder | O `TARGET` aceita um host arbitrário, escreve num campo oculto e usa como redirecionamento pós-autenticação. Domínio real, login real, credencial real, e o redirecionamento só dispara depois. | [PoC](https://github.com/r000t1ng/Host-Manipulation-Siteminder) |
| **XSS refletido**<br>Loja Integrada | O filtro roda antes da normalização, então os hífens de `s-v-g` sobrevivem à checagem e só caem fora no caminho para o DOM. Componente padrão de endereço, alcançado pelo `cep`. | [PoC](https://github.com/r000t1ng/loja-integrada-xss) |

### Reconhecimento

| Organização | Forma | Ano |
| :--- | :--- | :--- |
| **Unilever** | Hall of fame | 2023, 2025, 2026 |
| **Deutsche Bank** | Bounty pago | 2023, 2024, 2025 |
| **Linx** | Carta de agradecimento | 2025 |
| **[Nações Unidas](https://unite.un.org/en/ict-security/hall-fame)** | Hall of fame | 2024 |
| **[Motorola Solutions](https://www.motorolasolutions.com/en_us/about/security-vulnerability/hall-of-fame.html)** | Hall of fame | 2024 |
| **Dell** | Hall of fame | 2024 |
| **Harvard University** | Divulgação pública | 2024 |
| **NASA** | Carta, Vulnerability Disclosure Policy | 2022, 2023 |
| **iFood** | Hall of fame | 2021, 2022, 2023 |
| **Mastercard** | Hall of fame | 2023 |
| **IBM** | Hall of fame | 2023 |
| **Nubank** | Bounty pago | 2023 |
| **American Airlines** | Bounty pago | 2023 |
| **HackerOne** | Bounty pago | 2022 |
| **Riot Games** | Bounty pago | 2022 |
| **Drexel University** | Carta, escritório do CISO | 2022 |
| **LinkedIn** | Bounty pago | 2021 |
| **Uber** | Hall of fame | 2021 |
| **Receita Federal** | Divulgação pública | 2020 |
| **Razer** | Divulgação pública | 2020 |
| **Toyota** | Hall of fame | 2019 |
| **Telefônica Brasil** | Hall of fame | 2018 |
| **[Open Bug Bounty](https://www.openbugbounty.org/researchers/r00t1ng/)** | Outstanding Security Researcher | 2017 |

| Tipo | Detalhe |
| :--- | :--- |
| **Write up** | O [Estadão](https://bluestudioexpress.estadao.com.br/conteudo/2024/05/20/evento-discute-acoes-para-combater-fraudes-em-boletos-no-b2b/) escreveu sobre a pesquisa da NF-e e a fraude de boletos no B2B |
| **Open source** | Teste de intrusão no empacotamento do [OWASP ModSecurity CRS](https://innovatorsforopensuse.org/2023/09/05/owasp-modsecurity-crs-for-everyone-on-opensuse/) para openSUSE, verificando as proteções do Core Rule Set antes do lançamento |

### Palestras

| Ano | Palestra | Evento | Links |
| :--- | :--- | :--- | :--- |
| 2025 | Trusted Exploits: Escalando Ataques Usando Superfícies Confiáveis e Bypass de WAFs | OWASP São Paulo | [Assistir](https://www.youtube.com/watch?v=TFFCrLLabZQ) |
| 2024 | Fraude em Boletos no B2B | Simplifica+ Talks | [Assistir](https://www.youtube.com/watch?v=kkH-MCX9GBs) |
| 2022 | Bug Bounty: A Journey Behind the Bug | OWASP São Paulo | [Assistir](https://www.youtube.com/watch?v=QIsIGkduIBo) |
| 2019 | Segurança Defensiva | Anhanguera Educacional, presencial | |
| 2019 | Segurança Ofensiva | Anhanguera Educacional, presencial | |
| 2017 | Google Hacking e SQL Injection: Buscando vulnerabilidades pela web<br><sub>1.125 inscritos</sub> | 2º RootDay Web Conferência | [Página do evento](https://www.eventials.com/rootday/google-hacking-e-sql-injection-buscando-vulnerabilidades-pela-web/) |
| 2017 | Engenharia Social e o Uso dela atualmente | 2º RootDay Web Conferência | |

</details>

---

<sub>Everything here is published for education, defensive awareness and authorized security testing.</sub><br>
<sub><em>Tudo aqui é publicado para fins educacionais, conscientização defensiva e testes de segurança autorizados.</em></sub>
