---
title: States
weight: 2
---
<!-- Page Specific Styling -->
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

Write some stuff here about the data collected in `state`...

## Example

State data recorded to Firebase is experiment specific. It will look as follows:

```yaml
🞃 states: {
      # Unique session ID
    🞃 -O4bhX9wmx0cFlNK6ZZQ: {
        🞃 state: {
            # Experiment specific data
            🞂 board: {},
              currentPlayer: "O",
              firstArrival: "X",
              playerStarted: "O",
              round: 1,
              winner: " "
          },
      }
}
```

## Data

#### Unique Session ID
> Key value matching a unique session ID found in `sessions`

#### state
> Container for experiment specific data

#### Experiment Specific Data
> Data specific to an experiment which is defined by the experimenter in the javascript code


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
    url="../recorded-data/"
    title="Recorded Data"
    icon="server"
    subtitle="Saved data for analysis"
    >}}
{{< /cards >}}