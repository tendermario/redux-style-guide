# Mario's Redux Styleguide

This is the pattern I currently use!

Table of Contents
=================

   * [Mario's Redux Styleguide](#marios-redux-styleguide)
      * [Actions:](#actions)
         * [[action]](#action)
         * [[namespace]](#namespace)
         * [[additional_identifier]](#additional_identifier)
         * [[what_happened]](#what_happened)
      * [Action Creators](#action-creators)
      * [Thunks](#thunks)

## Actions:

`[action](_[additional_identifier])_[namespace]_[what happened]`

e.g.
```
CREATE_TOUR_REQUEST
CREATE_GROUPS_TOUR_REQUEST
```

### [action]

```
GET*_PROJECT_REQUEST
UPDATE_PROJECT_REQUEST
DELETE_PROJECT_REQUEST
CREATE**_PROJECT_REQUEST
```

*using `get` as it refers to an async http request (to me), whereas 'read' feels more like a synchronous action. So following crud except for 'read'.

**using `create` instead of `add` as I feel create is a stronger idea about creating something new. Add is a good alternative for when something that exists is being added to something.

### [namespace]

What resource this is under.

### [additional_identifier]

 Something additional needed to identify.

e.g.

```
CREATE_GROUPS_TOUR_REQUEST
```

### [what_happened]

This is for when an action is indicating what part of a thunk action it is at.

There's three main states, but the naming is flexible for more.
I don't know why, but I like "failed" more than "fail" even though the other terms aren't past tense.

```
[action]_[namespace]_REQUEST
[action]_[namespace]_SUCCESS
[action]_[namespace]_FAILED
```

## Action Creators

Same as the Actions except with camelCase:
```
getTourRequest
```

## Thunks
Same as Action Creators, except without the last word:
```
getTour
```