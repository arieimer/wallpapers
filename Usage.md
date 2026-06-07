# Usage

1. Add as an input to flake.nix

```nix
{
  inputs = {
    nixpkgs.url = "github:NixOS/nixpkgs/nixos-unstable";
    wallpapers = {
      url = "github:arieimer/wallpapers";
      flake = false;
    };
  };
}
```

2. Use it as needed

```nix
{ inputs, ... }: {
  # ${inputs.wallpapers}/wallpapers on nixos-rebuild will expand into the nix store directory containing all the wallpapers
  # usage can look like this
  programs.noctalia.settings.wallpaper.directory = "${inputs.wallpapers}/wallpapers";
}
```

# Showcase
