# Typescript Node - Proof Of Concept - XML Builder

## Installation

### Step 1
```bash
npx gts init -y
```

### Step 2
```bash
yarn add xmlbuilder
```

### Step 3
Read the [documentations](https://github.com/oozcitak/xmlbuilder-js/wiki)
and any [examples](https://github.com/oozcitak/xmlbuilder-js/wiki/Examples)

### Step 4
Execute a simple class with
```typescript
import { Create } from 'xmlbuilder';

export class XMLConstructor {
    // Create header of XML
    private doc = create({ version: 1.0, encoding: 'utf-8'});
    
    // Insert content in xml
    private getBody = (body: any) => this.doc.ele(body);
    
    /* 
     *  Close XML content, pretty property is optional 
     *  but it's more easy to read. In production it's better.  
     */
    private getClose = () => this.doc.end({ pretty: true });
} 
```

### Step 5
Try to create a simple XML such as
```xml
<?xml version="1.0" encoding="utf-8"?>
<news>
    <type type="daily news">
        <title type="main">
            Peace In Ukraine.
        </title>
        <title type="secondary">
            Vote In France Soon.
        </title>
    </type>
</news>
```

### Step 6
Try this
```typescript
export class XMLConstructor {
    private doc = create("mrss", { encoding: 'utf-8', headless: true });    
}
```

to result this

```xml
<mrss xmlns:at="http://purl.org/atompub/tombstones/1.0" xmlns:dcterms="http://purl.org/dc/terms/" xmlns:vimond="http://www.vimond.com/vimondFeedExtension/1.0" xmlns:fn="http://www.w3.org/2005/xpath-functions" xmlns:channelstore="http://www.vimond.com/vimondFeedExtension/1.0" xmlns:media="http://search.yahoo.com/mrss/" xmlns="http://www.w3.org/2005/Atom">
  <channel>
    <title>PEACH BLENDER</title>
    <link>https://peach.blender.org/</link>
    <description>Big Buck Bunny is a comedy about a well-tempered rabbit “Big Buck”, who finds his day spoiled by the rude actions of the forest bullies, three rodents. In the typical 1950ies cartoon tradition Big Buck then prepares for the rodents a comical revenge.</description>
    <item>
      <title>Big Buck Bunny</title>
      <link>https://download.blender.org/peach/bigbuckbunny_movies/</link>
      <media:group>
        <media:content url="https://download.blender.org/peach/bigbuckbunny_movies/BigBuckBunny_320x180.mp4" fileSize="64657027" type="video/mp4" expression="full">
          <media:player url="https://download.blender.org/peach/bigbuckbunny_movies/BigBuckBunny_320x180.mp4" width="320" height="180"/>
          <media:rating>nonadult</media:rating>
          <media:category>animation</media:category>
        </media:content>
        <media:content url="https://download.blender.org/peach/bigbuckbunny_movies/BigBuckBunny_640x360.m4v" fileSize="121283919" type="video/x-m4v" expression="full">
          <media:player url="https://download.blender.org/peach/bigbuckbunny_movies/BigBuckBunny_640x360.m4v" width="640" height="360"/>
          <media:rating>nonadult</media:rating>
          <media:category>animation</media:category>
        </media:content>
        <media:content url="https://download.blender.org/peach/bigbuckbunny_movies/big_buck_bunny_720p_h264.mov" fileSize="416751190" type="video/quicktime" expression="full">
          <media:player url="https://download.blender.org/peach/bigbuckbunny_movies/big_buck_bunny_720p_h264.mov" width="1280" height="720"/>
          <media:rating>nonadult</media:rating>
          <media:category>animation</media:category>
        </media:content>
        <media:content url="https://download.blender.org/peach/bigbuckbunny_movies/big_buck_bunny_1080p_stereo.avi" fileSize="714744488" type="video/x-msvideo" expression="full">
          <media:player url="https://download.blender.org/peach/bigbuckbunny_movies/big_buck_bunny_1080p_stereo.avi" width="1920" height="1080"/>
          <media:rating>nonadult</media:rating>
          <media:category>animation</media:category>
        </media:content>
        <media:thumbnail url="https://peach.blender.org/wp-content/uploads/bbb-splash.png" width="1920" height="1080"/>
        <media:thumbnail url="https://peach.blender.org/wp-content/uploads/rodents.png" width="1920" height="1080"/>
        <media:thumbnail url="https://peach.blender.org/wp-content/uploads/evil-frank.png" width="1920" height="1080"/>
        <media:thumbnail url="https://peach.blender.org/wp-content/uploads/bunny-bow.png" width="1920" height="1080"/>
        <media:thumbnail url="https://peach.blender.org/wp-content/uploads/rinkysplash.jpg" width="1920" height="1080"/>
        <media:thumbnail url="https://peach.blender.org/wp-content/uploads/its-a-trap.png" width="1920" height="1080"/>
        <dcterms:valid start="2022-03-18T15:14:37.521Z" end="1679152477521" scheme="W3C-DTF"/>
      </media:group>
    </item>
  </channel>
</mrss>
```

### STEP 7

Use this url with axios
```
https://jsonplaceholder.typicode.com/users/
```

with this result

```xml
<?xml version="1.0" encoding="utf-8"?>
<notebook>
    <entry>
        <user id="1" username="Bret" email="Sincere@april.biz">Leanne Graham</user>
        <address lat="-37.3159" lng="81.1496">
            <street>Kulas Light</street>
            <suite>Apt. 556</suite>
            <zipcode>92998-3874</zipcode>
            <city>Gwenborough</city>
        </address>
        <contact>
            <phone>1-770-736-8031 x56442</phone>
            <website>http://hildegard.org</website>
        </contact>
        <company catchPhrase="Multi-layered client-server neural-net" bs="harness, real-time, e-markets">Romaguera-Crona</company>
    </entry>
    <entry>
        <user id="2" username="Antonette" email="Shanna@melissa.tv">Ervin Howell</user>
        <address lat="-43.9509" lng="-34.4618">
            <street>Victor Plains</street>
            <suite>Suite 879</suite>
            <zipcode>90566-7771</zipcode>
            <city>Wisokyburgh</city>
        </address>
        <contact>
            <phone>010-692-6593 x09125</phone>
            <website>http://anastasia.net</website>
        </contact>
        <company catchPhrase="Proactive didactic contingency" bs="synergize, scalable, supply-chains">Deckow-Crist</company>
    </entry>
    <entry>
        <user id="3" username="Samantha" email="Nathan@yesenia.net">Clementine Bauch</user>
        <address lat="-68.6102" lng="-47.0653">
            <street>Douglas Extension</street>
            <suite>Suite 847</suite>
            <zipcode>59590-4157</zipcode>
            <city>McKenziehaven</city>
        </address>
        <contact>
            <phone>1-463-123-4447</phone>
            <website>http://ramiro.info</website>
        </contact>
        <company catchPhrase="Face to face bifurcated interface" bs="e-enable, strategic, applications">Romaguera-Jacobson</company>
    </entry>
    <entry>
        <user id="4" username="Karianne" email="Julianne.OConner@kory.org">Patricia Lebsack</user>
        <address lat="29.4572" lng="-164.2990">
            <street>Hoeger Mall</street>
            <suite>Apt. 692</suite>
            <zipcode>53919-4257</zipcode>
            <city>South Elvis</city>
        </address>
        <contact>
            <phone>493-170-9623 x156</phone>
            <website>http://kale.biz</website>
        </contact>
        <company catchPhrase="Multi-tiered zero tolerance productivity" bs="transition, cutting-edge, web, services">Robel-Corkery</company>
    </entry>
    <entry>
        <user id="5" username="Kamren" email="Lucio_Hettinger@annie.ca">Chelsey Dietrich</user>
        <address lat="-31.8129" lng="62.5342">
            <street>Skiles Walks</street>
            <suite>Suite 351</suite>
            <zipcode>33263</zipcode>
            <city>Roscoeview</city>
        </address>
        <contact>
            <phone>(254)954-1289</phone>
            <website>http://demarco.info</website>
        </contact>
        <company catchPhrase="User-centric fault-tolerant solution" bs="revolutionize, end-to-end, systems">Keebler LLC</company>
    </entry>
    <entry>
        <user id="6" username="Leopoldo_Corkery" email="Karley_Dach@jasper.info">Mrs. Dennis Schulist</user>
        <address lat="-71.4197" lng="71.7478">
            <street>Norberto Crossing</street>
            <suite>Apt. 950</suite>
            <zipcode>23505-1337</zipcode>
            <city>South Christy</city>
        </address>
        <contact>
            <phone>1-477-935-8478 x6430</phone>
            <website>http://ola.org</website>
        </contact>
        <company catchPhrase="Synchronised bottom-line interface" bs="e-enable, innovative, applications">Considine-Lockman</company>
    </entry>
    <entry>
        <user id="7" username="Elwyn.Skiles" email="Telly.Hoeger@billy.biz">Kurtis Weissnat</user>
        <address lat="24.8918" lng="21.8984">
            <street>Rex Trail</street>
            <suite>Suite 280</suite>
            <zipcode>58804-1099</zipcode>
            <city>Howemouth</city>
        </address>
        <contact>
            <phone>210.067.6132</phone>
            <website>http://elvis.io</website>
        </contact>
        <company catchPhrase="Configurable multimedia task-force" bs="generate, enterprise, e-tailers">Johns Group</company>
    </entry>
    <entry>
        <user id="8" username="Maxime_Nienow" email="Sherwood@rosamond.me">Nicholas Runolfsdottir V</user>
        <address lat="-14.3990" lng="-120.7677">
            <street>Ellsworth Summit</street>
            <suite>Suite 729</suite>
            <zipcode>45169</zipcode>
            <city>Aliyaview</city>
        </address>
        <contact>
            <phone>586.493.6943 x140</phone>
            <website>http://jacynthe.com</website>
        </contact>
        <company catchPhrase="Implemented secondary concept" bs="e-enable, extensible, e-tailers">Abernathy Group</company>
    </entry>
    <entry>
        <user id="9" username="Delphine" email="Chaim_McDermott@dana.io">Glenna Reichert</user>
        <address lat="24.6463" lng="-168.8889">
            <street>Dayna Park</street>
            <suite>Suite 449</suite>
            <zipcode>76495-3109</zipcode>
            <city>Bartholomebury</city>
        </address>
        <contact>
            <phone>(775)976-6794 x41206</phone>
            <website>http://conrad.com</website>
        </contact>
        <company catchPhrase="Switchable contextually-based project" bs="aggregate, real-time, technologies">Yost and Sons</company>
    </entry>
    <entry>
        <user id="10" username="Moriah.Stanton" email="Rey.Padberg@karina.biz">Clementina DuBuque</user>
        <address lat="-38.2386" lng="57.2232">
            <street>Kattie Turnpike</street>
            <suite>Suite 198</suite>
            <zipcode>31428-2261</zipcode>
            <city>Lebsackbury</city>
        </address>
        <contact>
            <phone>024-648-3804</phone>
            <website>http://ambrose.net</website>
        </contact>
        <company catchPhrase="Centralized empowering task-force" bs="target, end-to-end, models">Hoeger LLC</company>
    </entry>
</notebook>
```
