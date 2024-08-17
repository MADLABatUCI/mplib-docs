---
title: States
weight: 2
---
<style>
  a {
    text-decoration: none !important;
  }
  a mark {
    font-size: 1.25em;
    color: white;
  }
</style>
Add information about session metadata here.

```yaml
🞃 sessions: {
      # Unique session ID
    🞃 -O4Tzf-PJ5F8r1iVUmBk: {
        🞂 allPlayersEver: {},
          numPlayersEverJoined: 2,
          playerControl: "_8kzvxj11l",
        🞂 players: {},
          sessionIndex: 1,
          sessionStartedAt: 1723875637932,
          status: "active",
          timeElapsedToWaitingRoom: 2750,
          waitingRoomStartedAt: 1723875635286
    }
}
```
[==functionName==](/mplib-docs/)
: something

{{< spoiler text="Click to view the spoiler" >}}

This is the content of the details.

Markdown is **supported**.
```python
def function(param1):
  print("hello")
```

<p>Testing something <b>here</b></p>

{{< /spoiler >}}

The configuration of your site can be found in `config/_default/`.

<!--more-->

## Full Documentation

See https://docs.hugoblox.com/getting-started/customize/

## Navigation

### Menu

See https://docs.hugoblox.com/getting-started/customize/#menu-items

## Left Sidebar

Links are automatically generated from the structure of your content directory. Simply add a folder to nest a page.

### Extra Links

Additional links can be added under the `sidebar` section of your `config/_default/menus.yaml`:

```yaml
menu:
  sidebar:
    - name: "Need help?"
      params:
        type: separator
      weight: 1
    - name: "A page"
      pageRef: "/page-filename-here"
      weight: 2
    - name: "An external link ↗"
      url: "https://hugoblox.com"
      weight: 3
```

## Right Sidebar

A table of contents is automatically generated from the headings your Markdown file.

It can optionally be disabled by setting `toc: false` in the front matter of a page:

```yaml
---
title: My Page
toc: false
---
```
