# Repository Type and Provider for Boxen

Requires the following boxen modules:

Supports:

* git

## Usage

```puppet
repository {
  '/path/to/code':
    source   => 'user/repo', #short hand for github repos
    provider => 'git';
  'my emacs config':
    source   => 'git://github.com/wfarr/.emacs.d.git',
    path     => '/etc/emacs.d',
    provider => 'git',
}
```

## Caveats

Default boxen will set up some defaults for git that mercurial won't like,
to override them you can use:

```puppet
Repository <| provider == 'mercurial' |> {
  extra    => undef,
  config   => undef,
  require  => undef,
}
```
