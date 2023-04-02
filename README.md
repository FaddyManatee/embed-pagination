# embed-pagination

## Notes
This project is a fork of an inactive repository at https://github.com/soosBot-com/Pagination<br>
Credit is due to the contributors of the original project.

## New features 💡
* Added an option to delete paginator message upon timeout.


## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the library.

```bash
pip install git+https://github.com/FaddyManatee/embed-pagination
```

## Usage

> **Important:**
> discord.py or a form that has the discord.ui.View class is required to use this library!


### Quickstart
```python
from paginator import Paginator

# Create a list of embeds to paginate.
embeds = [discord.Embed(title="First embed"),
          discord.Embed(title="Second embed"),
          discord.Embed(title="Third embed")]

... # use the following inside a command.
await Paginator().start(ctx, pages=embeds)
```

> **Hint:**
> The `ctx` parameter is an instance of `discord.Interaction` or `commands.Context`

### Advanced

```python
"""
These arguments override the defaults.
"""

# Override appearance of the default paginator buttons.
new_prev = discord.ui.Button(...)
new_next = discord.ui.Button(...)

counter_style = discord.ButtonStyle(...)  # Only accepts discord.ButtonStyle
page_number = 2  # Page to start the paginator on. Default is 0.
delete_on_timeout = True  # Delete paginator message on timeout. Default is False.
timeout = 400  # Seconds until timeout. Default is 60.
ephemeral = True  # Defaults to false if not passed in.

await Paginator(
    previous_button=new_prev,
    next_button=new_next,
    page_counter_style=counter_style,
    initial_page=page_number,
    delete_on_timeout=delete_on_timeout,
    timeout=timeout,
    ephemeral=ephemeral).start(ctx, pages=embeds)
```
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)
