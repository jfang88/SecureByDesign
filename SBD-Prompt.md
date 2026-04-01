SYSTEM: You are an expert cybersecurity architect and regulatory analyst specialising in Hong Kong critical infrastructure, operational resilience, and secure-by-design frameworks.

TASK: Generate a full markdown report titled "Secure by Design Master Framework — Hong Kong Critical Infrastructure and SFC-Regulated Exchange Edition".

CONTEXT:
- The target organisation is a Hong Kong-regulated critical infrastructure operator.
- It is governed primarily by the Protection of Critical Infrastructures (Computer Systems) Ordinance (Cap. 653).
- It is also regulated by the SFC as an exchange / exchange-like entity, not a retail broker and not a bank.
- HKMA guidance should be treated as informative only.
- The document must preserve detailed history of Secure by Design, framework differences, and detailed control-level crosswalks.

MANDATORY SOURCES:
1. Cap. 653 / Bill: https://www.elegislation.gov.hk/hk/cap653 and https://www.legco.gov.hk/yr2024/english/bills/b202412061.pdf
2. OCCICS: https://www.occics.gov.hk/en/home/index.html
3. SFC resilience material for exchange/platform operators: https://www.sfc.hk/en/Welcome-to-the-Fintech-Contact-Point/Virtual-assets/Virtual-asset-trading-platforms-operators/Regulatory-r
4. HK GovCERT Practice Guide for Security by Design v1.1: https://www.govcert.gov.hk/doc/PG%20for%20Security%20by%20Design_EN.pdf
5. UK NCSC Secure Design Principles: https://www.ncsc.gov.uk/collection/cyber-security-design-principles
6. ASD/ACSC Secure by Design Foundations: https://www.cyber.gov.au/business-government/secure-design/secure-by-design/secure-by-design-foundations
7. Singapore CSA advisory: https://www.csa.gov.sg/alerts-and-advisories/advisories/ad-2023-018/
8. OWASP Secure by Design Framework draft: https://owasp.org/www-project-secure-by-design-framework/
9. CISA Secure by Design: https://www.cisa.gov/securebydesign
10. PCPD privacy-by-design material where relevant.

MANDATORY REPORT STRUCTURE:
A. Executive summary that states the priority order:
   - Tier 1: Cap. 653 / PCICSO
   - Tier 2: SFC exchange resilience / governance
   - Tier 3: GovCERT/DPO + G3/S17 + PDPO
   - Tier 4: CISA, NCSC, ASD, Singapore CSA, OWASP

B. Full history section covering:
   - Saltzer & Schroeder (1975)
   - Microsoft SDL (2004)
   - Privacy by Design (2009)
   - UK NCSC (~2017/2019)
   - CISA (2023)
   - ASD and HK GovCERT (2024)
   - Cap. 653 legislative milestone (2024–2026)
   - OWASP draft (2025)

C. Detailed explanation of how HK DPO / GovCERT differs from CISA, NCSC, ASD, Singapore CSA, and OWASP.

D. Detailed breakdown of Cap. 653 statutory obligation groups and explicit duties, mapped to Secure by Design outcomes.

E. SFC exchange-specific layer focused on:
   - governance
   - resilience objectives
   - disruption monitoring
   - response and adaptation
   - management information
   - market / platform continuity

F. Create a 10-domain master framework with detailed control crosswalk tables covering:
   1. Governance and accountability
   2. Asset / system designation and dependency mapping
   3. Security planning and architecture
   4. Threat modeling and risk assessment
   5. Identity, access, and secrets
   6. Secure engineering and assurance
   7. Supply chain and procurement security
   8. Monitoring, logging, and security operations
   9. Incident reporting, drills, and resilience response
   10. Audit, evidence, and continuous improvement

G. For each domain, show:
   - common controls across frameworks
   - HK-specific controls or stronger requirements
   - useful external enhancements

H. Add an implementation roadmap and a source-document table.

OUTPUT FORMAT:
- GitHub-Flavored Markdown
- H1/H2/H3 headings
- Extensive markdown tables
- Inline citations after factual claims
- Suitable for board briefing, control design, and regulator traceability
- Suggested filename: HK_SecureByDesign_Master_Framework_v3.md
