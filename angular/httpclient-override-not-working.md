# HttpClient override not working


## TLDR

You need to pass the options as `any` or `object`, not literal.

```typescript
// private http: HttpClient

...

// https://angular.io/api/common/http/HttpClient
// Overload #11
// Constructs a request which interprets the body as a Blob and returns the full HttpResponse.
const options: any = {
    responseType: 'blob',
    observe: 'response',
};
const observable: Observable<HttpResponse<Blob>> = this.http.get(url, options);

...

// Won't work. TypeScript will complain no override available.
const observable = this.http.get(url, { responseType: 'blob', observe: 'response' });
```


## The Story

The one issue that still linger in my head.
And the sole reason why I make this troubleshooting logs.

I don't know the actual problem and I don't care!

Yeah, I should probably report it.


## Reproduce

The example from the [HttpClient docs](https://angular.io/api/common/http/HttpClient).


## Environment

- Language:
    - typescript
- Framework:
    - angular


## Issue

- Degree: bug
- Keywords:
    - angular httpclient cannot override
    - download file with angular httpclient
- References: []
