<p align="center">
<a href="https://troubleshooting.tools/lookup/ip/"><img src="https://troubleshooting.tools/assets/img/troubleshooting.tools/gh_logo.png" height="200"></a>
</p>

# IP Address Lookup 

IP address lookup by troubleshootings.tools shows the public-facing IPv4 address by visiting the webpage with related information such as location, ISP, PTR record and much more. There are a variety of display options, starting on the web page itself, a preview of the link shared through a messenger or similar, or via API on a different web page or app.

## Content
<ol>
<li>) Web page</li>
<li>) Webhook</li>
<li>) Open Graph</li>
<li>) OpenSearch</li>
<li>) HTML search form</li>
<li>) API</li>
<li>) Limitations and caveats</li>
</ol>


## 1.) Web page

Explore your own public-facing IPv4 address
<ol>
<li>Visit with a web browser https://troubleshooting.tools/lookup/ip/</li>
<li>The page already display your public-facing IP address including all related informations</li>
</ol>

Explore any other public IPv4 address
<ol>
<li>Visit with a web browser https://troubleshooting.tools/lookup/ip/</li>
<li>Enter an IP address in the search form</li>
<li>Hit enter key or submit button</li>
</ol>


## 2.) Webhook

Beside the classic form input on the web page, the web page supports also webhooks. This possibility is ideal to share a link and guide the recipient directly to the results.

**URL:** **`https://troubleshooting.tools/lookup/ip/`** `{ipv4_address}` <br><br>
Example: `https://troubleshooting.tools/lookup/ip/8.8.4.4`

## 3.) Open Graph

Sharing the Webhook link into a web page or app that support the Open Graph protocol gives the opportunity to share a small excerpt of the results, without that the recipient need to visit the webpage itself.

Examples

Slack:<br>
<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opengraph/slack.jpg" style="width: 50%; height: 50%">

Discord:<br>
<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opengraph/discord.jpg" style="width: 50%; height: 50%">

Mattermost:<br>
<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opengraph/mattermost.jpg" style="width: 50%; height: 50%">

WhatsApp:<br>
<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opengraph/whatsapp.jpg" style="width: 50%; height: 50%">

Telegram:<br>
<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opengraph/telegram.jpg" style="width: 50%; height: 50%">

Twitter:<br>
<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opengraph/twitter.jpg" style="width: 50%; height: 50%">


## 4.) Open Search

The browser integration of troubleshooting.tools allows to use the browser address bar as a search input field, when needed, without visiting the original web page before.

This function is called OpenSearch and works with Apple Safari, Microsoft Edge, Mozilla Firefox and Google Chrome. Before we can start using it, we have to setup our browser for this function. Here an example for Google Chrome:

At the top right, click More <img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opensearch/0_menu.jpg"> and then **Settings**.

<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opensearch/1_google_chrome_settings.jpg">

Under "Search engine," click **Manage search engines**.

<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opensearch/2_manage_search_settings.jpg">

To the right of "Other search engines," click **Add**.

<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opensearch/3_search_engine_settings.jpg">

Fill out the text fields as shown below and click **Add**.

<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opensearch/4_edit_search_engine.jpg" align="right">

**Search engine:**<br>
`Enter troubleshooting.tools or a name of your choice.`

**Keyword:**<br>
`Enter the character "t" or a keyword of your choice, to trigger later the search function.`

**URL with %s in place of query:**<br>
`https://troubleshooting.tools/lookup/ip/%s`

<br><br><br><br><br>

The setup is complete. You are still able to continue to enter a URL in the address bar or any search terms that trigger a Google search.

<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opensearch/5_google_search_bar.jpg">

The new feature is, if you enter an "t" followed by a space, then you activate the troubleshooting.tools search.

<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opensearch/6_troubleshooting.tools_search_bar_a.jpg">

<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opensearch/7_troubleshooting.tools_search_bar_b.jpg">

This cause that Google Chrome address bar react like the search field on this website.

<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opensearch/8_troubleshooting.tools_search_bar_c.jpg">

## 5.) HTML search form

To integrate the search bar into a different web page a few line are needed. The look and feel can be adjusted as desired.

```html
<form method="post" action="https://troubleshooting.tools/lookup/ip/">
  <input type="text" name="IPADDRESS" placeholder="">
  <input type="submit" value="&#128269;">
</form>
```

## 6.) API

The API allows to integrate the results of the IP Address Lookup results on a different web page or app. Different formats and level of outputs are available, which can be adjust based on the need.

| Format | Level      | URL | Output |
| ----------------- |:------- | :---| :---|
| Plaintext   | 0 | `https://api.troubleshooting.tools/lookup/ip/` `{ipv4_address}` | IP Address |
| JSON   | 0 | `https://api.troubleshooting.tools/lookup/ip/json/` `{ipv4_address}` | IP Address, PTR Record |
| JSON   | 0 | `https://api.troubleshooting.tools/lookup/ip/json/lvl0/` `{ipv4_address}` | IP Address, PTR Record |
| JSON   | 1 | `https://api.troubleshooting.tools/lookup/ip/json/lvl1/` `{ipv4_address}` | IP Address, PTR Record, Country code/name, Region name, City Name, Latitude, Longitude |
| JSON   | 2 | `https://api.troubleshooting.tools/lookup/ip/json/lvl2/` `{ipv4_address}` | IP Address, PTR Record, Country code/name, Region name, City Name, Latitude, Longitude, ISP, Network Range, CIDR, Name, Handle, Autonomous System (AS) |

#### Plaintext Example:

##### Endpoint: "Automatic discovery"

  ``` BASH
  https://api.troubleshooting.tools/lookup/ip/
  ```

##### Example Request:

  ``` BASH
  curl -X GET https://api.troubleshooting.tools/lookup/ip/
  ```

##### Example Response:

  ```BASH
  102.216.69.156
  ```

---

##### Endpoint: "IP Address Lookup"

  ``` BASH
  https://api.troubleshooting.tools/lookup/ip/{ipaddress}
  ```

##### Example Request:

  ``` BASH
  curl -X GET https://api.troubleshooting.tools/lookup/ip/8.8.4.4
  ```

##### Example Response:

  ```BASH
  8.8.4.4
  ```

---

##### Example Response, when IP Address is invalid:

  ```BASH
  Invalid IP address
  ```

##### Example Response, when IP address is not public and therefore reserved:

  ```BASH
  Reserved IP address
  ```

---

#### JSON Example:

##### Endpoint: "Automatic discovery"

  ``` BASH
  https://api.troubleshooting.tools/lookup/ip/json/
  ```

##### Example Request:

  ``` BASH
  curl -X GET https://api.troubleshooting.tools/lookup/ip/json/
  ```

##### Example Response:

  ```BASH
  {
    "ip": "102.216.69.156",
    "invalid": false,
    "reserved": false,
    "ptr_record": "No PTR record found"
  }
  ```

##### Endpoint: "IP Address Lookup"

  ``` BASH
  https://api.troubleshooting.tools/lookup/ip/json/{ipaddress}
  ```

##### Example Request:

  ``` BASH
  curl -X GET https://api.troubleshooting.tools/lookup/ip/json/8.8.4.4
  ```

##### Example Response:

  ```JSON
  {
    "ip": "8.8.4.4",
    "invalid": false,
    "reserved": false,
    "ptr_record": "dns.google"
  }
  ```

##### Example Response, when IP Address is invalid:

  ```JSON
  {
    "ip": "8.8.4.256",
    "invalid": true,
    "reserved": false
  }
  ```

##### Example Response, when IP address is not public and therefore reserved:

  ```JSON
  {
    "ip": "192.168.1.1",
    "invalid": false,
    "reserved": true,
    "additional_context": {
      "address_block": "192.168.0.0/16",
      "name": "Private-Use",
      "rfc": "RFC1918",
      "allocation_date": "1996-02"
    }
  }
  ```
---

##### Endpoint: "Automatic discovery" Level 1

  ``` BASH
  https://api.troubleshooting.tools/lookup/ip/json/lvl1/
  ```

##### Example Request:

  ``` BASH
  curl -X GET https://api.troubleshooting.tools/lookup/ip/json/lvl1/
  ```

##### Example Response:

  ```BASH
  {
    "ip": "102.216.69.156",
    "invalid": false,
    "reserved": false,
    "ptr_record": "No PTR record found",
    "location_data": {
      "ipVersion": 4,
      "ipAddress": "102.216.69.156",
      "latitude": -1.28333,
      "longitude": 36.816669,
      "countryName": "Kenya",
      "countryCode": "KE",
      "timeZone": "+03:00",
      "zipCode": "-",
      "cityName": "Nairobi",
      "regionName": "Nairobi City"
    }
  }
  ```

##### Endpoint: "IP Address Lookup"

  ``` BASH
  https://api.troubleshooting.tools/lookup/ip/json/lvl1/{ipaddress}
  ```

##### Example Request:

  ``` BASH
  curl -X GET https://api.troubleshooting.tools/lookup/ip/json/lvl1/8.8.4.4
  ```

##### Example Response:

  ```JSON
  {
    "ip": "8.8.4.4",
    "invalid": false,
    "reserved": false,
    "ptr_record": "dns.google",
    "location_data": {
      "ipVersion": 4,
      "ipAddress": "8.8.4.4",
      "latitude": 37.386051,
      "longitude": -122.083847,
      "countryName": "United States of America",
      "countryCode": "US",
      "timeZone": "-07:00",
      "zipCode": "94035",
      "cityName": "Mountain View",
      "regionName": "California"
    }
  }
  ```

##### Example Response, when IP Address is invalid:

  ```JSON
  {
    "ip": "8.8.4.256",
    "invalid": true,
    "reserved": false
  }
  ```

##### Example Response, when IP address is not public and therefore reserved:

  ```JSON
  {
    "ip": "192.168.1.1",
    "invalid": false,
    "reserved": true,
    "additional_context": {
      "address_block": "192.168.0.0/16",
      "name": "Private-Use",
      "rfc": "RFC1918",
      "allocation_date": "1996-02"
    }
  }
  ```
---

##### Endpoint: "Automatic discovery" Level 2

  ``` BASH
  https://api.troubleshooting.tools/lookup/ip/json/lvl2/
  ```

##### Example Request:

  ``` BASH
  curl -X GET https://api.troubleshooting.tools/lookup/ip/json/lvl2/
  ```

##### Example Response:

  ```JSON
  {
    "ip": "102.216.69.156",
    "invalid": false,
    "reserved": false,
    "ptr_record": "No PTR record found",
    "location_data": {
      "ipVersion": 4,
      "ipAddress": "102.216.69.156",
      "latitude": -1.28333,
      "longitude": 36.816669,
      "countryName": "Kenya",
      "countryCode": "KE",
      "timeZone": "+03:00",
      "zipCode": "-",
      "cityName": "Nairobi",
      "regionName": "Nairobi City"
    },
    "registry_data": {
      "netRange": "102.216.68.0 - 102.216.69.255",
      "cidr": "102.216.68.0/23",
      "name": "not provided",
      "handle": "102.216.68.0 - 102.216.69.255",
      "parent": "102.216.68.0 - 102.216.71.255",
      "netType": "ASSIGNED PA",
      "originAS": "not provided",
      "lastChanged": "Thu, 23 Nov 2023 06:40:00 GMT",
      "remark": "not provided",
      "isp": "not provided",
      "country": "KE",
      "address": "Airtel Networks Kenya Limited, Nairobi, Other",
      "source": "https://search.arin.net/rdap/?query=102.216.69.156"
    }
}
  ```

##### Endpoint: "IP Address Lookup"

  ``` BASH
  https://api.troubleshooting.tools/lookup/ip/json/lvl2/{ipaddress}
  ```

##### Example Request:

  ``` BASH
  curl -X GET https://api.troubleshooting.tools/lookup/ip/json/lvl2/8.8.4.4
  ```

##### Example Response:

  ```JSON
  {
    "ip": "8.8.4.4",
    "invalid": false,
    "reserved": false,
    "ptr_record": "dns.google",
    "location_data": {
      "ipVersion": 4,
      "ipAddress": "8.8.4.4",
      "latitude": 37.386051,
      "longitude": -122.083847,
      "countryName": "United States of America",
      "countryCode": "US",
      "timeZone": "-07:00",
      "zipCode": "94035",
      "cityName": "Mountain View",
      "regionName": "California"
    },
    "registry_data": {
      "netRange": "8.8.4.0 - 8.8.4.255",
      "cidr": "8.8.4.0/24",
      "name": "GOGL",
      "handle": "NET-8-8-4-0-2",
      "parent": "NET-8-0-0-0-0",
      "netType": "DIRECT ALLOCATION",
      "originAS": "not provided",
      "lastChanged": "Thu, 28 Dec 2023 22:24:56 GMT",
      "remark": "not provided",
      "isp": "Google LLC",
      "country": "not provided",
      "address": "1600 Amphitheatre Parkway, Mountain View, CA, 94043, United States",
      "source": "https://search.arin.net/rdap/?query=8.8.4.4"
    }
  }
  ```

##### Example Response, when IP Address is invalid:

  ```JSON
  {
    "ip": "8.8.4.256",
    "invalid": true,
    "reserved": false
  }
  ```

##### Example Response, when IP address is not public and therefore reserved:

  ```JSON
  {
    "ip": "192.168.1.1",
    "invalid": false,
    "reserved": true,
    "additional_context": {
      "address_block": "192.168.0.0/16",
      "name": "Private-Use",
      "rfc": "RFC1918",
      "allocation_date": "1996-02"
    }
  }
  ```


Error handling:
* ```Invalid IP address```
  * Every input that can\'t be identified as IPv4 address will trigger an error message.
* ```Reserved IP address```
  * Address Blocks that matches with the following [list](https://www.iana.org/assignments/iana-ipv4-special-registry/iana-ipv4-special-registry.xhtml) will trigger an error message.
* ```HTTP 429: Too Many Requests```
  * Rate limit: 250 requests per second.
  * This limit may be adjusted without prior notice based on server resource demand.

## 7.) Limitations and caveats

### IPv6
- IPv6 detection is not supported.
- IPv6 lookup support is considered, but not planned.

---
All mentioned trademarks are the property of their respective owners.
