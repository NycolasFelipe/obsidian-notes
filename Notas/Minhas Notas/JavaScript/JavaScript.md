## [[Array Reduce]]

## [[Search when press Enter]]

.flat(Infinity).length
```
let params = new URLSearchParams(document.location.search);
let name = params.get("name");
```

    const birthDayString = contact.birthday;

    const year = birthDayString.substring(0, 4);

    const month = birthDayString.substring(5, 7);

    const day = birthDayString.substring(8, 10);

    const date = new Date(year, month, day);

    date.setMonth(date.getMonth() - 1);

    setBirthday(prevState => ({ ...prevState, value: date }));

```
import { useEffect } from "react";

  

/**

 * Hook that handles clicks outside of the passed ref

 */

const useOutsideClick = (ref, setState) => {

  useEffect(() => {

    function handleClickOutside(event) {

      if (ref.current && !ref.current.contains(event.target)) {

        setState(false);

      }

    }

    // Bind the event listener

    document.addEventListener("mousedown", handleClickOutside);

    return () => {

      // Unbind the event listener on clean up

      document.removeEventListener("mousedown", handleClickOutside);

    };

  }, [ref]);

}

  

export default useOutsideClick;
```