## Context Manager

it requires function to return a context manager. This lang feature acts as function with lifecycle events:

with EXPRESSION as TARGET:
    SUITE

Classic example:

```py
with open("file.txt") as f:
    data = f.read()
```

Here the file is:
- opened before the block
- available as f inside the block
- automatically closed after the block

Simple Custom Context Manager

```py
class MyResource:
    def __enter__(self):
        print("enter")
        return self

    def __exit__(self, exc_type, exc, tb):
        print("exit")

with MyResource() as r:
    print("inside")

# Order:
# enter
# inside
# exit
```

### contextlib

Return `conn` to the caller (get_all_users) to run query. As soon as query ends, the control goes back to `get_connection` for cleanup (__aexit__).


```py
from contextlib import asynccontextmanager

@asynccontextmanager
async def get_connection():
    conn = await acquire_db_connection()
    try:
        yield conn
    finally:
        await release_db_connection(conn)

async def get_all_users():
    async with get_connection() as conn:
        return conn.query('SELECT ...')
```
