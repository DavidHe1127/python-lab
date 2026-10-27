# Python Lab

## Standard

```py
def describe(color, size):
    print(color, size)

options = {"color": "red", "size": "L"}
describe(**options)

# red L
```

- globals().get('FUNCTION_NAME') then call it FUNCTION_NAME()


- ternary operator like ? :
```
result = tool(**arguments) if tool else {}
```

- slice operator `:`.

```python
numbers = [10, 20, 30, 40, 50]

numbers[:3]
# [10, 20, 30]

```

- unpack tuple

```python
return (
    updated_transcript,
    render_transcript(updated_transcript),
    reply.conversation_id,
    "",
    reply.message_count,
)

updated_transcript, rendered_transcript, new_conversation_id, cleared_input, message_count = (
    await send_message(message, conversation_id, transcript)
)
```
