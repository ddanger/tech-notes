# Notes from Open Source North 2019

<p align="center">
    <a href="https://daviddangerfield.smugmug.com/Things/i-4jz3VXJ/A">
        <img
            alt="GitHub Logo - Statue of Liberty"
            src="https://photos.smugmug.com/Things/i-4jz3VXJ/2/373d181d/S/IMG_20190523_092253-S.jpg">
    </a>
</p>

## tl;dr
- Before writing code, consider **Market Risk** -- the risk that **nobody. even. cares!**
- Checkout [Percy.io](https://percy.io)($) for visual testing (visual match)
- Use `eslint-plugin-react-hooks`
- SSR is complex. Next.js/Nuxt.js remove _some_ complexity
- GitHub invests in sticker design. Very smart.

## Sessions
### Testing Lessons from Failed Projects
#### Todd Gardner
- Market risk (the risk that nobody wants to use the expensive software you build) is a thing.
  - Need to test all ideas against real user behaviour _before_ investing $$$$$ in development
  - Consider the following to guage market interest: Landing pages, beta launches, small realeases, etc.
- Test the scariest thing first. This is the thing that may doom the project in the end. Deal with it ASAP.
- Don't test to achieve metrics. The metric is your own confidence. It cannot be measured.

### Cypress: Where Automated Web UI Testing Isn't Just for QA Anymore
#### Justin James
- Devs can do cypress UI testing.
- What does QA do?
  - Stress, Security, Accessibility, Using the UI in unexpected way,
- Visual testing
  - [Percy.io](https://percy.io)
- Accessibility
  -`cy.injectAxe()`, `cy.checkA11y()`

### The Power of Hooks in React
#### Aaron Ackerman
- Late 2015: Stateless Functional Components
- Feb 2019: Reactv16.8.0 Hooks
- useState
- useContext
- useEffect
- useReducer
- useRef
- Use eslint-plugin-react-hooks

### What's New With Vue?
#### Casie Siekman
- Vue 3:
  - word on the street is that Vuex mutations are going away? Maybe not in Vue 3 but in Vuex 4

### Practical Single Page Apps with SSR Using Next.js
#### Matt Ruby
- React SSR framework
- Awesome, but still, running React on both server and client is no picnic.

## Sponsors
### GitHub table
- GitHub was there mostly to encourage usage of GitHub Enterprise
- I mentioned IBM who they said is one of their biggest Enterprise clients
- They had *a ton* of different sticker designs with the GitHub logo. The coolest (to me)
was a GitHub statue of liberty. Shown above.

<p align="center">
    <a href="https://daviddangerfield.smugmug.com/Things/i-XJ5XM4P/A">
        <img
            alt="GitHub logo stickers"
            src="https://photos.smugmug.com/Things/i-XJ5XM4P/1/fc84f939/S/IMG_20190522_150421~2-S.jpg">
    </a>
</p>

### Code 42 table
- They are developing ways to secure data so that if your disgruntled employees
steal your files and copy them places, they have a record and can intervene.
- I mentioned IBM might want something like that. They said IBM is one of their
largest clients.
- I get it, but it's quite big brotherish
