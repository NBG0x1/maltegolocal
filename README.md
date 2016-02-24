# Maltegolocal
Local Transform Wrapper for Maltego

**authors: Stuart Kennedy / @noobiedog**
**authors: Glenn Wilkinson / @Glennzw**
**company: Sensepost / @sensepost**

#### NOTE: Still under development.

Please see the Paterva / Maltego documentaion [HERE](https://www.paterva.com/web6/documentation/developer-local.php) for more information on Local Transforms

## Settings for the local transform

![alt text](https://github.com/adam-p/markdown-here/setup.jpg "Setup")

## Sample Transform

``` go
package main

import (
	"github.com/noobiedog/maltegolocal"
	"fmt"
	"os"
)

func main() {

	TRX := maltegolocal.MaltegoTransform{}
	Domain := os.Args[1]
	NewEnt := TRX.AddEntity("maltego.Domain", "Hello" + Domain)
	NewEnt.SetType("maltego.Domain")
	NewEnt.SetValue(Domain)
	NewEnt.AddDisplayInformation("<h3>Heading</h3><p>content here about" + Domain + "!</p>", "Other")
	NewEnt.AddProperty("Display Value", Domain, "nostrict", "True")
	NewEnt.SetLinkColor("#FF0000")
	NewEnt.SetWeight(200) 
	NewEnt.SetNote("Domain is " + Domain)
	TRX.AddUIMessage("completed!","Inform")
 	fmt.Println(TRX.ReturnOutput())
}
```
