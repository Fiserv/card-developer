# Test Cases

<span style="color:#ff6600;">**Company API Endpoints**</span>

## Company Notes

Tests must use only requests given here.

### Company Notes v1: Search company notes

This API returns a list with one or multiple company notes with summary information.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/notes/search

```
{
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000",
   "startDate": "2024-01-31",
   "endDate": "2024-02-07"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "notes": [
      {
         "noteId": "01",
         "operatorIdentifier": "VSA",
         "date": "2024-02-02",
         "text": "CREDIT LIMIT INCREASED"
      }
   ]
}
```

### Company Notes v1: Add company notes

This API is for adding company notes

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/notes

```
{
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000",
   "text": "CREDIT LIMIT INCREASED"
}
```

#### Response

**HTTP Code:** 201 Created

```
{
   "noteId": "01",
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000",
   "text": "CREDIT LIMIT INCREASED"
}
```

### Company Notes v1: Update company note

This API is used for updating company notes.

#### Request

**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/notes

```
{
    "identifier": "001",
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "noteType": "NOTE",
    "text": "This is company note"
}
```

#### Response

**HTTP Code:** 204 No Content

### Company Notes v1: Search company memos

This API returns a list with one or multiple company memos with summary information.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/companies/v1/memos/search

```
{
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000",
   "startDate": "2024-01-31",
   "endDate": "2024-02-07"
}
```

#### Response

**HTTP Code:** 200 OK

```
{
   "memos": [
      {
         "memoId": "01",
         "operatorIdentifier": "VSA",
         "date": "2024-02-01",
         "text": "CREDIT LIMIT INCREASED"
      }
   ]
}
```

### Company Notes v1: Add company memos

This API is for adding company memos.

#### Request

**HTTP METHOD:** POST

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/memos

```
{
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000",
   "text": "CREDIT LIMIT DECREASED"
}
```

#### Response

**HTTP Code:** 201 Created

```
{
   "memoId": "01",
   "companyIdentifier": "TEST0002",
   "systemIdentifier": "3771",
   "principalIdentifier": "0050",
   "agentIdentifier": "0000",
   "text": "CREDIT LIMIT DECREASED"
}
```

### Company Notes v1: Update company memo

This API is used for updating company memos.

#### Request

**HTTP METHOD:** PATCH

**Target URL:** https://card-sandbox.api.fiservapps.com/cs/companies/v1/notes

```
{
    "identifier": "001",
    "companyIdentifier": "TEST0002",
    "systemIdentifier": "3771",
    "principalIdentifier": "0050",
    "agentIdentifier": "0000",
    "noteType": "MEMO",
    "text": "Update Company Memo1"
}
```

#### Response

**HTTP Code:** 204 No Content
