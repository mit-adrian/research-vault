---
filename: "{{item.citekey}}"
---

Year: {{date | format("YYYY")}}
Authors: {{authors}}

Title: {{title}}
URL: {{url}}
Zotero Link: {{pdfZoteroLink}}

---

{% for annotation in annotations -%}
{% if annotation.annotatedText -%}
> "{{annotation.annotatedText}}"
> _{{annotation.type | capitalize}}_ on page {{annotation.page}}{% if annotation.colorCategory %} ({{annotation.colorCategory}}){% endif %}

{%- endif %}

{%- if annotation.imageRelativePath %}
![[{{annotation.imageRelativePath}}]]
{%- endif %}

{%- if annotation.comment %}
**Comment:** {{annotation.comment}}
{%- endif %}

{%- if annotation.allTags %}
**Tags:** {{annotation.allTags}}
{%- endif %}

---

{%- endfor %}





