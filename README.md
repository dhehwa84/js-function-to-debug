# js-function-to-debug


```javascript
// function definitions
      
       var stackHolder = {
          count: 3,
          storage: [1, '{id: 1,value: "obj"}', "stringHolder", 46],
        };


        var push = function (value) {
          stackHolder.storage.push(value);
          stackHolder.count++;
          return stackHolder.storage;
        };

        var pop = function () {
          if (stackHolder.count === 0) {
            return [];
          }

          var poppedItem = stackHolder.storage[stackHolder.count];
          delete stackHolder.storage[stackHolder.count];
          stackHolder.count--;
          return stackHolder.storage;
        };

        var peek = function () {
          return [stackHolder.storage[stackHolder.count]];
        };

        var swap = function () {
          var temp = stackHolder.storage[0];
          stackHolder.storage[0] = stackHolder.storage[stackHolder.count];
          stackHolder.storage[stackHolder.count] = temp;
          return stackHolder.storage;
        };

      function stack(stackOperation, stackValue) {
        switch (stackOperation) {
          case "push":
            return push(stackValue);
            break;
          case "pop":
          return pop();
            break;
          case "swap":
          return swap();
            break;
          case "peek":
          return peek();
            break;
          default:
            return stackHolder.storage;
        }
      }

      // keep this function call here
      console.log("push: " + stack("push", 42));
      console.log("pop: " + stack("pop"));
      console.log("swap: " + stack("swap"));
      console.log("peek: " + stack("peek"));
      console.log("default: " + stack(""));
```
