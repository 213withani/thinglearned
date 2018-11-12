# react-dates
## airbnb prop types
https://twitter.com/ljharb/status/827237520505122816 
```Let’s say `Foo` takes a “bar” prop. `<Foo barr />` becomes an error, immediately exposing your typo.```
Example: https://github.com/airbnb/react-dates/blob/master/src/components/CalendarWeek.jsx
``` const propTypes = forbidExtraProps({
  children: or([childrenOfType(CalendarDay), childrenOfType(CustomizableCalendarDay)]).isRequired,
}); ```
