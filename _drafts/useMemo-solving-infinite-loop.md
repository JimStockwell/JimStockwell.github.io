Using "useMemo" to wrap my `Array.from(columns)` before giving it useTable solved an infinite loop.
My current theory on why is: maybe Array.from creates a new reference on earch render, which causes, well, a new render.

- Is this an accurate explanation?
- Is this only an issue with useTable, or is it more general with React?

Here is the memoized code that works:

```
    const columnsWithDelete = useMemo(() => {
        const x = columns.concat();
        x.push({
            Header: 'db',
            accessor: "delete-button",
            Cell: row => (
                <button>Delete</button>
            )
        });
        return x;
    }, [columns]);
    
    const tableInstance = useTable({ columns: columnsWithDelete, data, defaultColumn, updateMyData })
```

where columns was in our `props`.
