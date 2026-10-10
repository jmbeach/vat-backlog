---
id: vat-awd
---

A bullet that already has a [vat-xxx] ID may have new indented notes added beneath it in
backlog.md at any time — even when an items/vat-xxx.md already exists from a prior sync.
On the next vat sync those notes should be appended to the existing item file (or create
it if absent), then the note lines collapsed as usual. This lets humans and agents enrich
a task after it's been assigned without needing to edit the item file directly.
