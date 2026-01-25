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

## Jak uruchomić (high level)
1. Importuj workflow JSON do n8n (Workflows → Import)
2. Ustaw credentials: Airtable + Google Drive + ConvertAPI
3. Skonfiguruj endpoint webhook (np. /generuj)
4. Wykonaj test na 1 rekordzie

## Wymagane integracje
- n8n
- Airtable
- Google Drive
- ConvertAPI
- (opcjonalnie) własna usługa renderująca DOCX

## Bezpieczeństwo
Repo zawiera wersję “sanitized” — bez sekretów. Wstaw swoje credentials w n8n.

## Backend 
(coming soon) – repo workflow + dokumentacja, a serwis renderujący
