## Usage

The database can be downloaded and directly imported to automate the use of boilerplates.

## Populating database

It is following a simple schema that can be described by this interface :

```ts
interface Collection {
  // Each technology has its own collection object
  [technologyName: string]: {
    repositories: {
      // GitHub repository name
      name: string;
      // GitHub description
      description: string;
      // GitHub author
      author: string;
      // GitHub repository's URL
      url: string;
      // Metadata that can be used to find a specific repository
      metadata: {
        // Keywords that references other technologies or principles besides the main technology in the repository
        keywords: string[];
        // (GitHub stars) low = < 500 | medium >= 500 and < 1000 | high >= 1000
        popularity: "low" | "medium" | "high";
      };
    }[];
  };
}
```

For now, each entry has to be added or modified directly from this .json file.
