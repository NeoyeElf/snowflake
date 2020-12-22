snowflake
====
Forked from [bwmarrin/snowflake](https://github.com/bwmarrin/snowflake)

### Installing

```sh
go get github.com/NeoyeElf/snowflake
```

### Usage

**Example Program:**

```go
package main

import (
	"fmt"
	"github.com/NeoyeElf/snowflake"
)

func main() {

	// Create a new Node with a Node number of 1
	node, err := snowflake.NewNode(1)
	if err != nil {
		fmt.Println(err)
		return
	}

	// Generate a snowflake ID.
	id := node.Generate()

	// Print out the ID in a few different ways.
	fmt.Printf("Int64  ID: %d\n", id)
	fmt.Printf("Base2  ID: %s\n", id.Base2())
	fmt.Printf("Base64 ID: %s\n", id.Base64())
}
```

### What's new
You can use custom NodeId Bits and Sequence ID Bits

```go
node, err := snowflake.NewNode(1, WithCustomBits(8, 14))
```

