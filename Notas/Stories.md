**A story captures the rendered state of a UI component**. It's an object with annotations that describe the component's behavior and appearance given a set of arguments.
## Where to put stories
A component’s stories are defined in a **story file that lives alongside the component file**. The story file is for development-only, and it won't be included in your production bundle. In your filesytem, it looks something like this:
```
components/
├─ Button/
│  ├─ Button.js | ts | jsx | tsx | vue | svelte
│  ├─ Button.stories.js | ts | jsx | tsx
```
## Component Story Format
We define stories according to the [Component Story Format](https://storybook.js.org/docs/api/csf) (CSF), an ES6 module-based standard that is easy to write and portable between tools.
### Default export
The _default_ export metadata controls how Storybook lists your stories and provides information used by addons. For example, here’s the default export for a story file `Button.stories.js|ts`:
```tsx
import type { Meta } from '@storybook/react';

import { Button } from './Button';

const meta: Meta<typeof Button> = {
  component: Button,
};

export default meta;
```
> The _default_ export **must contain a `title` property**.
### Defining stories
Use the _named_ exports of a CSF file to define your component’s stories. We recommend you use UpperCamelCase for your story exports. Here’s how to render `Button` in the “primary” state and export a story called `Primary`.
```tsx
import type { Meta, StoryObj } from '@storybook/react';

import { Button } from './Button';

const meta: Meta<typeof Button> = {
  component: Button,
};

export default meta;
type Story = StoryObj<typeof Button>;

export const Primary: Story = {
  args: {
    primary: true,
    label: 'Button',
  },
};
```
#### Working with React Hooks
[React Hooks](https://react.dev/reference/react) are convenient helper methods to create components using a more streamlined approach. You can use them while creating your component's stories if you need them, **although you should treat them as an advanced use case**. ==We **recommend** [args](https://storybook.js.org/docs/writing-stories/args) as much as possible when writing your own stories==. As an example, here’s a story that uses React Hooks to change the button's state:
```tsx
import React, { useState } from 'react';

import { Meta, StoryObj } from '@storybook/react';

import { Button } from './Button';

const meta: Meta<typeof Button> = {
  component: Button,
};

export default meta;
type Story = StoryObj<typeof Button>;

/*
 * Example Button story with React Hooks.
 * See note below related to this example.
*/
const ButtonWithHooks = () => {
  // Sets the hooks for both the label and primary props
  const [value, setValue] = useState('Secondary');
  const [isPrimary, setIsPrimary] = useState(false);

  // Sets a click handler to change the label's value
  const handleOnChange = () => {
    if (!isPrimary) {
      setIsPrimary(true);
      setValue('Primary');
    }
  };
  return <Button primary={isPrimary} onClick={handleOnChange} label={value} />;
};

export const Primary: Story = {
  render: () => <ButtonWithHooks />,
};
```
### Rename stories
You can rename any particular story you need. For instance, to give it a more accurate name. Here's how you can change the name of the `Primary` story:
```tsx
import type { Meta, StoryObj } from '@storybook/react';

import { Button } from './Button';

const meta: Meta<typeof Button> = {
  component: Button,
};

export default meta;
type Story = StoryObj<typeof Button>;

export const Primary: Story = {
  // 👇 Rename this story
  name: 'I am the primary',
  args: {
    label: 'Button',
    primary: true,
  },
};
```
>Your story will now be shown in the sidebar with the given text.
