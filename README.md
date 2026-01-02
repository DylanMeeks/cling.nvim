# cling.nvim

![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/juniorsundar/cling.nvim/lint-test.yml?branch=main&style=for-the-badge)
![Lua](https://img.shields.io/badge/Made%20with%20Lua-blueviolet.svg?style=for-the-badge&logo=lua)

`cling.nvim` allows you to wrap CLI commands, providing structured output buffers and recursive help-based completions.

## Installation

Using [lazy.nvim](https://github.com/folke/lazy.nvim):

```lua
{
  "juniorsundar/cling.nvim",
  config = function()
    require("cling").setup({
      wrappers = {
        {
          binary = "docker",
          command = "Docker",
          help_cmd = "--help",
        },
        {
          binary = "jj",
          command = "JJ",
          completion_cmd = "jj util completion bash",
        },
        {
          binary = "eza",
          command = "Eza",
          completion_file = "https://raw.githubusercontent.com/eza-community/eza/refs/heads/main/completions/bash/eza",
        }
      },
    })
  end,
}
```

