# React Native Light DatePicker
[![install size](https://packagephobia.now.sh/badge?p=rn-lightweight-date-picker)](https://packagephobia.now.sh/result?p=rn-lightweight-date-picker) <a href="https://codeclimate.com/github/roman-sereda/react-native-light-datepicker/test_coverage"><img src="https://api.codeclimate.com/v1/badges/7c85ed35de65972f2131/test_coverage" /></a> <a href="https://codeclimate.com/github/roman-sereda/react-native-light-datepicker/maintainability"><img src="https://api.codeclimate.com/v1/badges/7c85ed35de65972f2131/maintainability" /></a> [![Build Status](https://travis-ci.org/roman-sereda/react-native-light-datepicker.svg?branch=develop)](https://travis-ci.org/roman-sereda/react-native-light-datepicker)

<img src="https://media.giphy.com/media/cPTicQKsaMlxFc7udk/giphy.gif" data-canonical-src="https://media.giphy.com/media/cPTicQKsaMlxFc7udk/giphy.gif" width="366.3" height="300" />

Lightweight date range picker with not dependencies for React Native.
## Install
```sh
$ npm i rn-lightweight-date-picker --save
```
## Example
```javascript

  state = {
    minDate: new Date(2018, 12, 31)
  }

  onChange(data){
    const { start, end } = data;
    if(start && data) api.fetchSchedule(start, end);
  }
  
  render(){
    return(
      <Calendar
        locale = "ru"
        userStyles = {{ topBar: { controls: 'flex-start' }}}
        userColors = {{ title: 'blue' }}
        maxRange = {10}
        minDate = {this.state.minDate}
        onDateChange={this.onChange}
        format="dd.mm.yyyy"
      />
    )
  }
```
## Contributing
Feel free to open new issues if you have any problems or suggestions.

## Properties
All properties are optional

| Prop | Type | Default | Desc |
:------------ |:---------------| :-----| :-----|
| **`locale`** | `String` | Device language | Calendar localization. |
| **`onDateChange`** | `Function` | (date) => {} | Returns chosen date. Range mode: `{start: value, end: value}`, single: `value`. `value`: if date selected - `Date object`, if selected and format specified - `String`, if not selected - `false`.|
| **`format`** | `String` or `false` | false | Example: `"dddd. mmmm - yyyy"`. See below for details. |
| **`userColors`** | `Object`| {} | Override colors. See below for details. |
| **`userStyles`** | `Object`| {} | Override styles. See below for details. |
| **`minRange`** | `Number` or `false` | false | Minimum avaliable size of selected range. |
| **`maxRange`** | `Number` or `false` | false |  Maximum avaliable size of selected range. |
| **`minDate`** | `Date` or `false` | false | Minimum avaliable date to be selected. . |
| **`maxDate`** | `Date` or `false` | false | Maximum avaliable date to be selected. |
| **`mode`** | `String` | `range` | `single` or `range`. Give opportunity to select only one date or range(In range you can select one date too). |
| **`fadeDuration`** | `Number` | 300 | Month switching duration in ms. |
| **`initialDate`** | `Date` | new Date() | This date will be shown in calendar on load. Default is Current Time. |
| **`leftControl`** | `Component` | `<Text>{ "<" }</Text>` | Specified left control. |
| **`RightControl`** | `Component` | `<Text>{ ">" }</Text>` | Specified right control. |
| **`highlightToday`**| `Bool` | true | Specified if current date should be highlighted. |
| **`rowheight`**| `Number` | 30 | Week height in calendar. |
| **`rowPadding`**| `Number` | 7 | Week padding in calendar. |

## Styles
All styles could be overwritten. If you want you can also easily change only colors. Below you can see what values are responsible for styles or colors, you can override them in `userStyles` or `userColors`.(Components are colorized just to facilitate understanding)
<img src="https://i.imgur.com/Ny7RfCF.png" />

## Date format
Example `dd dddd mmmm : yyyy` will become `01 Sunday September : 2019`.

| Prop | Type | Default | Desc | Default | Desc |
:------------ |:---------------| :-----| :-----|:-----| :-----|
| `dn` | T | `mn` | S | `yy` | 19 |
| `d` | 1-31| `m` | 1-12 | `yyyy` | 2019 |
| `dd` | 01-31| `mm` | 01-12 |||
| `ddd` | Thu | `mmm` | Sep |||
| `dddd` | Thursday| `mmmm` | September |||

