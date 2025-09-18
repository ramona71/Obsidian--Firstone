- The `dir()` function _returns all properties and methods of the specified object_, without the values 
# Pickle file
A **pickle file** is a file created using Python’s built-in **`pickle`** module. It is used to **serialize** (save) and **deserialize** (load) Python objects.
- **Serialization** = converting a Python object (like a list, dict, model, etc.) into a byte stream so it can be stored in a file or sent over a network.
- **Deserialization** = loading that byte stream back into the original Python object.
### Where it's used
- Saving trained **machine learning models**.
- Storing **Python dictionaries, lists, objects**.
- Transferring Python objects between programs.
⚠️ **Note**: Pickle files are **Python-specific** and not secure against malicious input. Never unpickle data from an untrusted source.
```python
import pickle

# Example object
data = {"name": "Alice", "age": 25, "skills": ["Python", "SQL", "ML"]}

# Save (serialize) to pickle file
with open("data.pkl", "wb") as f:   # "wb" = write binary
    pickle.dump(data, f)

# Load (deserialize) from pickle file
with open("data.pkl", "rb") as f:   # "rb" = read binary
    loaded_data = pickle.load(f)

print(loaded_data)
# Output: {'name': 'Alice', 'age': 25, 'skills': ['Python', 'SQL', 'ML']}
```
