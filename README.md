# Technical test specifications

## Animation for the pokemon image

The animation of the pokemon image is according to how much you scrolled. Considering we do not scroll much for a lot of
pokemon since all information normally fits in one screen, we need to play some tricks to better demonstrate the full
animation.

**To see full animation**: Go in `pokemonDetails.tsx` at line 26 there is the `MAX_MOVE_COUNT` constant. Put its value
to `30`. Then go to any pokemon details page and scroll down.

## Linting

Normally we would agree as a team to for the coding standards like if we use `;` in typescript and the spacing between
brackets (`[]`). We would then implement a linter for the standards. In this test, I did not pay any specific attention
to the linting.

## Tests

I would normally add unit tests for each component and functions added to the service. It was specified that we did not
need to do tests for this technical test, so I did not add any.

# Instructions

- Please fork this repo on your preferred git source
- Details of what is asked is all here, in the README
- Take all the time you need
- We'll exchange feedback when you're done
- If you have any questions, feel free to contact us
- Have fun!

---
---
---

> 💯 The technical test is the equivalent of user story.

# **💡 Context**

In POKE-1, the infinite list was implemented. We now have the `Pokemons` page, with all Pokemons listed. Not a lot of
information is available though, so we need a screen to list the details of a Pokemon.

# **✅ Acceptance criteria**

### Header

> 💡 You may or may not need to change the `PageContainer` component

- We need to see the image of the Pokemon.
    - When scroll is at 0, the image is centered and takes ~25% of the screen height.
    - When scrolling, it gradually (with an animation) moves to the top right to be ~32x32.
- The name of the Pokemon should be at the top center of the header, no animations.

### Content

- The content of the page should contain three sections:
    1. The types of the Pokemon
    2. The first 5 moves of the Pokemon
    3. The Pokemon evolutions
        - They should be pressable, and by pressing them we should navigate to the details screen of this Pokemon.

# ℹ️ Additional information

- Loading states are up to you
- Architecture is up to you
- File structure is up to you
- Libraries used are up to you

# 💻 Technical details

- For image:
    - use the `front_default` image from the `sprites` attributes on `https://pokeapi.co/api/v2/pokemon/${id}`
- For type:
    - `types` attribute on `https://pokeapi.co/api/v2/pokemon/${id}`
- For moves
    - `moves` attribute on `https://pokeapi.co/api/v2/pokemon/${id}`
- For evolutions
    - Fetch the `pokemon-species` from `https://pokeapi.co/api/v2/pokemon-species/${id}`
    - Fetch the according `evolution_chain.url`
    - The result is a nested `chain` of evolutions
        - Get the id from the `species.url` and the name to build the evolution’s UI card
        - Filter out the Pokemon that is currently displayed

# 💅🏻 Design files

https://www.figma.com/file/QONuuN2K6TuUZ6OqRmwtS0/Pokemon-details?type=design&node-id=0-1&mode=design&t=Gb22Mil3mNeqYAg1-0
