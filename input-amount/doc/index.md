# Input Amount

Amount input field Webcomponent.

```js script
import { html } from '~/core';
import { Required, Validator } from '@lion/form-core';
import { loadDefaultFeedbackMessages } from '@lion/validate-messages';
import '~/doc-styles';
import '../simba-input-amount.js';

loadDefaultFeedbackMessages();
```

```js preview-story
export const input = () => html`
  <simba-input-amount
    .validators=${[new Required()]}
    name="donation_amount"
    help-text="Donation amount"
  ></simba-input-amount>
`;
```

## Amount Restrictions

You can import and apply specific `NumberValidator`s, like `MinNumber`, `MaxNumber` or `MinMaxNumber` to constrain the allowed amounts.

```js preview-story
import { MinNumber } from '@lion/form-core';

export const inputMinimum = () => html`
  <simba-input-amount
    .validators=${[new Required(), new MinNumber(100)]}
    name="price"
    help-text="Must exceed 100"
  ></simba-input-amount>
`;
```

```js preview-story
import { MinMaxNumber } from '@lion/form-core';

export const inputRange = () => html`
  <simba-input-amount
    .validators=${[new Required(), new MinMaxNumber({ min: 100, max: 1000 })]}
    name="price"
    help-text="Must be in the range of 100 - 1000"
  ></simba-input-amount>
`;
```

## Disabled

You can also prefill and disable the amount in case you don't want your user to change it.

```js preview-story
export const inputDisabled = () => html`
  <simba-input-amount
    name="price"
    help-text="Preconfigured price"
    .modelValue=${123.45}
    disabled
  ></simba-input-amount>
`;
```
