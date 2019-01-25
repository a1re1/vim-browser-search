# vim-searchme

A naive Vim/Neovim plugin to open browser and search text directly.

### Install

```vim
Plug 'voldikss/vim-searchme'
```

### Usage

- **Basic**

    Use `<Leader>s` in operator-pending mode to search a word (for example, `<Leader>saw` to search a word). `<Leader>s` in visual mode to search for what you have selected. (for example, if you selected strings inside a bracket using `vas`, just type `<Leader>s` to search it).

    Also you may try `<Leader>S`, with which you can input what you want to search.

- **Commands**

    | command | introduction |
    | --- | --- |
    |`SearchCurrentText [search engine]`  | Search text under the cursor                   |
    |`SearchVisualText [search engine]`   | Search selected text                           |
    |`Search [search engine] {text}`      | Search text (using specified search engine)    |
    |`SearchInGithub {text}`              | Search text in [GitHub](https://github.com)    |
    | `SearchInZhihu {text}`              | Search text in [Zhihu](https://www.zhihu.com/) |
    | `...`                               |...                                             |

- **Define your own commands**

    ```vim
    " Template
    command!  -nargs=+  '[command name]'  :call searchme#SearchIn(<q-args>, '[search engine name]')
    " Example
    command!  -nargs=+  SearchInGoogle  :call searchme#SearchIn(<q-args>, 'google')
    ```

- **Specify your default search engine**
    ```vim
    " Template
    let g:search_engine = "[search engine name]" "default: 'google'
    ```

- **Add more search engines**

    ```vim
    " Template
    let g:query_map_added = {
            \ '[search engine name]': '[query url]'
            \}
    " Example
    let g:query_map_added = {
            \ 'wikipedia': 'https://en.wikipedia.org/wiki/{query}'
            \}
    ```

### Todo

-   [x] Support operator-pending mode
