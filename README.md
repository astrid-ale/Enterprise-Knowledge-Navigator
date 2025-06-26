# Cloud-Knowledge-Navigator
AI-Powered Unified Search for Enterprise Cloud Data

Project Goal

Enable users to retrieve information from stored cloud documents (Google Drive, Sheets, PDFs, etc.) via natural language queries, eliminating manual file searches while maintaining access control with google tools.

Success Metrics:

    Time Saved: Reduction in average search time per query (e.g., from 10 mins to <30 secs).

    Adoption Rate: % of active users/month.

    Accuracy: Precision/recall of answers against ground-truth data.

    Scalability: Max concurrent queries without latency.

Data Pipeline: Filtering, Escalation, Normalization
1. Data Ingestion & Filtering

    Scope: Limit to approved Google Drive folders (via FOLDER_ID).

    File Types: Prioritize structured (Sheets, Docs) over unstructured (PDFs, images).

    Permissions: Enforce drive.readonly scope; exclude files user lacks access to.

2. Data Escalation

    Priority Tiers:

        Tier 1: Frequently accessed files (e.g., "Sales Q1 2024.xlsx").

        Tier 2: Department-specific docs (HR, Finance).

        Tier 3: Archived/legacy files (processed on-demand).

3. Normalization & Preprocessing

    Structured Data (Sheets):

        Flatten tables into CSV-like strings.

        Preserve headers as metadata (e.g., [SALES_DATA] Product, Revenue).

    Unstructured Data (PDFs):

        Use Document AI API for OCR (scanned PDFs → text).

        Extract clean text, remove footers/headers.

    Metadata: Append file name, last modified date, and owner to context.

4. Proof of Concept
5. Impact
