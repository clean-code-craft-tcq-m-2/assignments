# Strong tests - recap

## T-shirt sizes

Which is right? 

`assert(size(38) == 'S');` or `assert(size(38) == 'M');`

- Reason out. Confirm assumptions with stakeholders
- It doesn't matter... let's do something and wait for someone to shout
- Don't make me think... tell me what to do

## Testing alignment

[Separation of forming from printing](https://github.com/clean-code-craft-tcq-4/test-failer-in-c-deepasn08/blob/4a093441acf91f1100ba220c57ac93f542ac5bd1/misaligned.c)

Think of another name, instead of `temp_list`

```python
def make_color_map():
    temp_list = []
    for i, major in enumerate(major_colors):
        for j, minor in enumerate(minor_colors):
            # Save the output into a list
            temp_list.append(f'{i * 5 + j} | {major} | {minor}')
```

## Consider off-the-shelf functionality

When tests are tough to write, see if you can use off-the-shelf functionality.
E.g., why not use comma-separated values? Import it into excel for alignment and printing.
