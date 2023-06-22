# (In/Eth)scription Collections Repository

## The only place for creators &amp; builders to organize (in/eth)scription collections

## Getting Started

**_Artists_**

Collection creators can format their collection data using the `inscriptions.json` and `meta.json` format below to be listed on all platforms using the standard!

**_Steps_**

1. Create your `inscriptions.json` and `meta.json` files in the format provided below
   - Check out [this handy tool](https://ordinals-metadata-composer.vercel.app/) to make the files fast & effortlessly!
2. Create a pull request to this repository including new collections that follow the standard

## File Structure

```
 .
 ├── ...
 └── collections
     └── [collection-slug]
          ├── inscriptions.json         <--  Required
          └── meta.json                 <--  Required
          └── logo.png                  <--  Optional
```

## Collection Metadata `meta.json`

```
{
  "name": "",                    # Collection name
  "inscription_icon": "",        # (optional) an inscription id in your collection to display as collection logo
  "supply": "",                  # total supply
  "slug": "",                    # directory name. all lowercase, '-' instead of spaces.
  "description": "",             # (optional) collection description
  "twitter_link": "",            # (optional) official twitter
  "discord_link": "",            # (optional) official discord
  "website_link": "",            # (optional) official website
  "background_color": ""         # (optional) default background color if your inscriptions have transparent background.
}
```

If you don't want to use one of your inscription as your collection logo, you can submit a separate logo file under your collection directory in this repo called `logo.png`.
It must be in png format with less than 512 x 512 px size.

## Inscription Data `inscriptions.json`

```
[
  {
    "id": "",                    # inscription id
    "meta": {
      "name": "",                 # inscription name,
      "status": "",               # (optional) inscription theme
      "rank":                     # (optional) inscription rarity rank
      "high_res_img_url":         # (optional) high resolution image if you have hosted offchain
      "attributes": [             # (optional) attributes associated with this inscription
        {
          "trait_type": "",        # trait type
          "value": "",             # trait value
          "status": "",            # (optional) trait theme
          "percent": ""            # (optional) percent of inscriptions in collection with trait
        },
        ...
      ]
    }
  },
  ...
]
```

## Here is an example of a completed collection inscription

Your meta.json file will look like this:

```
{
  "name": "Ethereum Rocks",
  "inscription_icon": "c63313b5bff17467742a13b2abe5002c14c40c531b4ed39d908ed64ffce8276ei0",
  "supply": "100",
  "slug": "ethereum-rock",
  "description": "A set of 100 distinct art pieces residing on the Ethereum Blockchain",
  "twitter_link": "https://twitter.com/RockEthscript",
  "discord_link": "https://discord.gg/dpzeYkAa27",
  "website_link": "",
  "background_color": "#C3FF02",
}
```

Your inscriptions.json file will look like this:

```
[
  {
    "id": "0xf32f9269ebcd62c2bf83e0e9608ed9bc94bbd30da629833f93318e75690c4eb3",
    "meta": {
      "name": "Ethereum Rock #0",
      "attributes": [
        {
          "trait_type": "collection",
          "value": "Ethereum Rocks"
        }
      ]
    },
    "number": "0"
  },
  {
    "id": "0xbacfbb7b29431044639f457d9368a4a4e2d560369902c02fdd3d72ec4eac63d0",
    "meta": {
      "name": "Ethereum Rock #1",
      "attributes": [
        {
          "trait_type": "collection",
          "value": "Ethereum Rocks"
        }
      ]
    },
    "number": "1"
  },
 ...
]
```
