---
title: Data
weight: 3
sidebar:
  open: true
---

This section contains information about how data is collected by MPLib.js and saved in Firebase.
There are three main aspects to data collection (sessions, states, and recorded data). These
three data collection components are described below. You can find more specific information about
the respective components in their own sub-pages.

## Sessions

A session is ...

{{< cards >}}
  {{< card
    url="sessions/"
    title="Sessions"
    icon="bookmark"
    subtitle="Metadata relevant to an experiment"
    >}}
{{< /cards >}}


## States

A state is ...

{{< cards >}}
  {{< card
    url="states/"
    title="States"
    icon="cube"
    subtitle="Experiment specific data"
    >}}
{{< /cards >}}


## Recorded Data

Recorded data is the permanetly saved version of a state. It has the same structure as state data,
however, it is saved under its own key value `recordedData`. Additionally, every update that is
made to state data will be saved under a unique key in `recordedData`.

{{< cards >}}
  {{< card
    url="recorded-data/"
    title="Recorded Data"
    icon="server"
    subtitle="Saved data for analysis"
    >}}
{{< /cards >}}
