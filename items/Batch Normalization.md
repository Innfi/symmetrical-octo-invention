>[!question]
>no direct explanation about why this works...?

```
normalized_data = (data - np.mean(data, axis=...)) / np.std(data, axis=...)
```

- internal covariant shift
