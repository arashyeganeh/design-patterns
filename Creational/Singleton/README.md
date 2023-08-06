![design-pattern-singleton](image/header.jpg)

# Singleton

The Singleton pattern guarantees the existence of just a single, unique instance of a class throughout your program's execution. It enforces the constraint of having only one instance of a particular object, preventing multiple copies. This singular instance is known as the singleton.

## benefits

- Ensures that just one instance is created from a class and
- Allow global access to the instance that is created
- To limit concurrent access to a shared resource.
- To create a global point of access for a resource.

## Use cases of a Singleton

Here are some instances where a singleton class finds practical application:

- Handling a database connection.
- Global point access to writing log messages
- File Manager

## Code

### Javascript

```javascript
class Singleton {
  static instance;

  constructor() {
    if (!Singleton.instance) {
      Singleton.instance = this._createInstance();
    }
    return Singleton.instance;
  }

  _createInstance() {
    // Private methods and properties can be defined here
    return {
      getInfo: () => {
        console.log("This is a Singleton instance.");
      },
      // Add more methods and properties as needed
    };
  }
}

// Usage
const singletonInstance1 = new Singleton();
const singletonInstance2 = new Singleton();

console.log(singletonInstance1 === singletonInstance2); // Output: true

singletonInstance1.getInfo(); // Output: This is a Singleton instance.
singletonInstance2.getInfo(); // Output: This is a Singleton instance.
```

### Python

```python
class Singleton:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
            # cls._instance.init()  # Call an initialization method
        return cls._instance

    def __init__(self):
        print("A")
        # Perform instance initialization here
        # This method will be called only once during the first instantiation
        pass


# Example usage
if __name__ == "__main__":
    instance1 = Singleton()
    instance2 = Singleton()

    print("Instance 1:", instance1)
    print("Instance 2:", instance2)

    print("Are instances the same?", instance1 is instance2)
```

