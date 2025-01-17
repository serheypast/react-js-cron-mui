## ReactJS Cron
> This package is based on Xavier Rutayisire package (https://github.com/xrutayisire/react-js-cron). Most if not all of the credit should go to him.
> A React cron editor built with [Material-UI](https://www.npmjs.com/package/@material-ui/core)

[![npm package](https://img.shields.io/npm/v/react-js-cron-mui/latest.svg)](https://www.npmjs.com/package/react-js-cron-mui)
[![MIT License Badge](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/levyitay/react-js-cron-mui/blob/master/LICENSE.md)

Live **demo** and **usage** at [https://levyitay.github.io/react-js-cron/](https://levyitay.github.io/react-js-cron-mui/?path=/docs/reactjs-cron--demo)

![react-js-cron example](https://raw.githubusercontent.com/levyitay/react-js-cron-mui/master/react-js-cron-example.png)

## Features

- Zero dependencies except React and Material-UI
- Supports all standard cron expressions
- Supports cron names for months and week days
- Supports cron shortcuts
- Supports "7" for Sunday
- Supports two-way sync binding with input
- Supports locale customization
- Supports multiple selection by double-clicking on an option
- And many more (disabled, read-only, 12-hour clock...)

## Inspired by

- [jqCron](https://github.com/arnapou/jqcron)
- [cron-converter](https://github.com/roccivic/cron-converter)

## Installation

Be sure that you have these dependencies on your project:
* react (>=16.8.0)
* material-ui (>=4.0.0)

```bash
# Yarn
yarn add react-js-cron-mui

# NPM
npm install --save react-js-cron-mui
```

## TypeScript

react-js-cron is written in TypeScript with complete definitions

## Usage

Learn more with [dynamic settings](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--dynamic-settings).

- [Two-way sync binding with input](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--input)
- [Default value](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--default-value)
- [Default period](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--default-period)
- [Disabled mode](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--disabled)
- [Read-Only mode](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--read-only)
- [Humanized labels](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--humanize-labels)
- [Humanized value](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--humanize-value)
- [Leading zero for numbers](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--leading-zero)
- [Error management with text and style](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--track-error)
- ["Clear button" removal](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--no-clear-button)
- ["Clear button" action](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--clear-button-empty-value)
- [Empty value management](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--empty-never-allowed)
- [Cron shortcuts](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--shortcuts)
- [12-hour clock](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--twelve-hour-clock)
- [24-hour clock](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--twenty-four-hour-clock)
- [Locale customization](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--french-locale)
- [Prefix and suffix removal](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--no-prefix-and-suffix)
- [Style customization](https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--custom-style)

## API

```
CronProps {
  /**
   * Cron value, the component is by design a controlled component.
   * The first value will be the default value.
   * 
   * required
   */
  value: string

  /**
   * Set the cron value, similar to onChange.
   * The naming tells you that you have to set the value by yourself.
   * 
   * required
   */
  setValue: 
    | (value: string) => void
    | Dispatch<SetStateAction<string>>

  /**
   * Set the container className and used as a prefix for other selectors.
   * Available selectors: https://levyitay.github.io/react-js-cron-mui/?path=/story/reactjs-cron--custom-style
   */
  className?: string

  /**
   * Humanize the labels in the cron component, SUN-SAT and JAN-DEC.
   * 
   * Default: true
   */
  humanizeLabels?: boolean

  /**
   * Humanize the value, SUN-SAT and JAN-DEC.
   * 
   * Default: false
   */
  humanizeValue?: boolean

  /**
   * Add a "0" before numbers lower than 10.
   * 
   * Default: false
   */
  leadingZero?: boolean | ['month-days', 'hours', 'minutes']

  /**
   * Define the default period when the default value is empty.
   * 
   * Default: 'day'
   */
  defaultPeriod?: 'year' | 'month' | 'week' | 'day' | 'hour' | 'minute' | 'reboot'

  /**
   * Disable the cron component.
   *
   * Default: false
   */
  disabled?: boolean
  
  /**
   * Make the cron component read-only.
   * 
   * Default: false
   */
  readOnly?: boolean

  /**
   * Define if empty should trigger an error.
   * 
   * Default: 'for-default-value'
   */
  allowEmpty?: 'always' | 'never' | 'for-default-value'

  /**
   * Support cron shortcuts.
   * 
   * Default: ['@yearly', '@annually', '@monthly', '@weekly', '@daily', '@midnight', '@hourly']
   */
  shortcuts?: boolean | ['@yearly', '@annually', '@monthly', '@weekly', '@daily', '@midnight', '@hourly', '@reboot']

  /**
   * Define the clock format.
   */
  clockFormat?: '12-hour-clock' | '24-hour-clock'

  /**
   * Display the clear button.
   * 
   * Default: true
   */
  clearButton?: boolean

  /**
   * antd button props to customize the clear button.
   */
  clearButtonProps?: ButtonProps

  /**
   * Define the clear button action.
   *
   * Default: 'fill-with-every'
   */
  clearButtonAction?: 'empty' | 'fill-with-every'

  /**
   * Display error style (red border and background).
   * 
   * Display: true
   */
  displayError?: boolean

  /**
   * Triggered when the cron component detects an error with the value.
   */
  onError?: 
    | (error: {
      type: 'invalid_cron'
      description: string
    }) => void
    | Dispatch<SetStateAction<{
      type: 'invalid_cron'
      description: string
    }>>
    | undefined

  /**
   * Change the component language.
   * Can also be used to remove prefix and suffix.
   *
   * When setting 'humanizeLabels' you can change the language of the
   * alternative labels with 'altWeekDays' and 'altMonths'.
   *
   * The order of the 'locale' properties 'weekDays', 'months', 'altMonths'
   * and 'altWeekDays' is important! The index will be used as value.
   *
   * Default './src/locale.ts'
   */
  locale?: {
    everyText?: string
    emptyMonths?: string
    emptyMonthDays?: string
    emptyMonthDaysShort?: string
    emptyWeekDays?: string
    emptyWeekDaysShort?: string
    emptyHours?: string
    emptyMinutes?: string
    emptyMinutesForHourPeriod?: string
    yearOption?: string
    monthOption?: string
    weekOption?: string
    dayOption?: string
    hourOption?: string
    minuteOption?: string
    rebootOption?: string
    prefixPeriod?: string
    prefixMonths?: string
    prefixMonthDays?: string
    prefixWeekDays?: string
    prefixWeekDaysForMonthAndYearPeriod?: string
    prefixHours?: string
    prefixMinutes?: string
    prefixMinutesForHourPeriod?: string
    suffixMinutesForHourPeriod?: string
    errorInvalidCron?: string
    weekDays?: string[]
    months?: string[]
    altWeekDays?: string[]
    altMonths?: string[]
  }
}
````

## License

MIT © [serheypast](https://github.com/serheypast)
  
