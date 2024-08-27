---
title: Recorded Data
weight: 3
---
<style>
  a {
    text-decoration: none !important;
  }

  a mark {
    font-size: 1.25em;
    color: white;
  }

  .prose :where(blockquote p):not(:where([class~=not-prose],[class~=not-prose] *)) {
    font-style: normal;
    font-weight: normal;
  }

  .prose :where(blockquote p:first-of-type):not(:where([class~=not-prose],[class~=not-prose] *)):before {
    content: unset;
  }

  .prose :where(blockquote p:last-of-type):not(:where([class~=not-prose],[class~=not-prose] *)):after {
    content: unset;
  }
</style>

<!-- Page Content -->

Write some stuff here about the data collected in `recordData`...

## Example

Recorded data takes a similar structure to the data recorded by `states`. However, there is
additional metadata that is collected. It will look as follows:

```yaml
🞃 recordedData: {
      # TODO
    🞃 -O4Tzf-PJ5F8r1iVUmBk: {
        🞂 allPlayersEver: {},
        🞂 players: {},
    }
}
```

## Events

## Players

<!-- Links to other sections -->
## Other Sections

{{< cards >}}
  {{< card
    url="../sessions/"
    title="Sessions"
    icon="bookmark"
    subtitle="Metadata relevant to an experiment"
    >}}

  {{< card
    url="../states/"
    title="States"
    icon="cube"
    subtitle="Experiment specific data"
    >}}
{{< /cards >}}