# A.A.E.P.W
Automatyczny Agregator Edytor Plików Word

## Co to robi?
Workflow w n8n automatyzuje generowanie dokumentów promocyjnych:
- pobiera dane z Airtable
- buduje payload (m.in. tabela produktów)
- pobiera szablony DOCX z Google Drive
- renderuje DOCX przez usługę HTTP (/render, /replace-image)
- konwertuje DOCX → PDF (ConvertAPI)
- zapisuje pliki do Google Drive
- aktualizuje status w Airtable (Work / Done / Error)

## Workflow
  A[Trigger: Cron/Webhook] --> B[Pobierz rekordy z Airtable]
  B --> C[Walidacja danych + mapowanie pól]
  C --> D[Pobierz szablon DOCX z Google Drive]
  D --> E[Render DOCX: /render + /replace-image]
  E --> F[Konwersja DOCX -> PDF (ConvertAPI)]
  F --> G[Zapis plików do Google Drive]
  G --> H[Aktualizacja statusu w Airtable: DONE]

  C -->|błąd danych| X[Log + status ERROR]
  E -->|błąd renderu| X
  F -->|błąd konwersji| X
  G -->|błąd zapisu| X
  
## Wymagane integracje
- n8n
- Airtable
- Google Drive
- ConvertAPI
- (opcjonalnie) własna usługa renderująca DOCX

## Bezpieczeństwo
Repo zawiera wersję “sanitized” bez sekretów. Wstaw swoje credentials w n8n.

## Backend 
(coming soon) – repo workflow + dokumentacja, a serwis renderujący
