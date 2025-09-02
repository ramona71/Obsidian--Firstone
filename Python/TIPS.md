- don't write all this
```python
def ceaser(direction,original_text,shift):
    if direction=="encode":
        encrypted_text=""
        for char in original_text:
            shift_position=(alphabet_list.index(char)+shift) % len(alphabet_list)
            encrypted_text+=alphabet_list[shift_position]
        print(encrypted_text)
  
    if direction=="decode":
        decrypted_text=""
        for char in original_text:
            shift_position=(alphabet_list.index(char)-shift) % len(alphabet_list)
            decrypted_text+=alphabet_list[shift_position]
        print(decrypted_text)
```
- always decrease the text, always, make it small as possible