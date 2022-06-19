---
title: std
version: 0.64.0
usage: |
  Creates a std expression for an aggregation
---

<script>
  import { usePageFrontmatter } from '@vuepress/client';
  export default { computed: { frontmatter() { return usePageFrontmatter().value; } } }
</script>

# <code>{{ frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ frontmatter.usage }}</div>

## Signature

```> std ```

## Examples

Std aggregation for a group by
```shell
> [[a b]; [one 2] [one 2] [two 1] [two 1]]
    | to-df
    | group-by a
    | agg (col b | std)
```