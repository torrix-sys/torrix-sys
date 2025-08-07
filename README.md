# Torrix

Torrix is a conceptional/experimental package manager, or a system distibution with it.

Torrix uses a decentralized distribution model, which does not use a centralizezd server unlike other operating systems.

For example, if you try `torrix install some_package`, the Torrix system tries to find a package from relays that you registered.

If there is a name collision, it will make you choose like following:

```
> torrix install some_package
There is a name collision. Which one are you searching for?
  1. some_package from [Relay 1] (https://...)
    - Torrix ID: abcd1234...
    - Author: Some Author 1
  2. some_package from [Relay 2] (https://...)
    - Torrix ID: efgh5678...
    - Author: Some Author 2
> 1
```

You can choose the specific package which you were looking for.

Or, without relay, you can install the package from Torrix ID directly.

```
torrix install some_package -id abcd1234...
```

With doing this, you can manage your system packages withouy relying on any centralized server.

Each 'Torrix Package' works like 'Torrix Git'.

Torrix Git is a git repository, which you can push to decentralized network, like torrent network.

But you can update the repository with public_key/private_key architecture.

Each Torrix Git will have a list of 'package@version' items, and the list can be updated by the original author.

Like Nix/Guix system, each 'package@version' can have other 'package@version' as dependencies.

Each 'package@version' will have `Torrix PKG ID`, and it will be shared on P2P network just like torrent.

That's why this is called 'Torrix'. It's basically 'Torrent + Nix/Guix'.

Also, if you have another idea, you can just simiply fork from pre-existing Torrix Package.

It will have different `Torrix ID`, and you can push it to relays you registered.

Each relays only have the list of metadata like Package Name(alias for Torrix ID), Torrix ID or Author Name, so the burden will not be huge for maintainers.

But at the early stage, the seeders might be not enough for P2P sharing.

For that, each relay maintainers can decide if they will accept the actual contents for seeding them.

```
Relay Type:
  1. No Seeding
  2. Early Seeding
  3. Maximum Sedding
```

'No Seeding' means that the relay will not participate in the P2P sharing.

In that case, the original author should maintain the seeding for a while.

'Early Seeding' means that the relay will seed for a while, but stop it if the number of seeders become enough.

'Maximum Seeding' means that the relay will keep seeding, no matter what the number of seeders is.

The best thing is just running your own relay.

You can whitelist authors, such as you or someone you trust.

```
Whitelisted Authors:
  You
  Your Friend
  Someone You Trust
```

Then it will try 'maximum seeding' for whitelisted authors.

With this Torrix distribution architecture, you will be able to have a completely decentralized software development model.

Also, there is an interesting Desktop Environment idea, which is based on the Torrix network.

To see more about it, consider seeing [Torrix Canvas](https://github.com/torrix-sys/torrix-canvas) desktop.
