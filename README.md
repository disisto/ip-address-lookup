<p align="center">
<a href="https://troubleshooting.tools/lookup/ip/"><img src="https://troubleshooting.tools/assets/img/gh_logo.gif" height="200"></a>
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

WhatsApp:<br>
<img src="https://github.com/disisto/IP-Address-Lookup/blob/main/img/opengraph/whatsapp.jpg" style="width: 50%; height: 50%">

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
| JSON   | 2 | `https://api.troubleshooting.tools/lookup/ip/json/lvl2/` `{ipv4_address}` | IP Address, PTR Record, Country code/name, Region name, City Name, Latitude, Longitude, RIR, Network Range, CIDR, Name, Handle, Autonomous System (AS) |

Error handling:
- Invalid input: Every input that can\'t be identified as IPv4 address will trigger an error message.
- Reserved IPs: Address Blocks that matches with the following [list](https://www.iana.org/assignments/iana-ipv4-special-registry/iana-ipv4-special-registry.xhtml)<sup>[1]</sup> will trigger an error message.
- Rate Limit: IP addresses of clients that make more than 250 requests/second<sup>[2]</sup> get blocked for 60 minutes.

## 7.) Limitations and caveats

### IPv4
- <sup>[1]</sup>Known bug: Not all reserved IPs based on the following [list](https://www.iana.org/assignments/iana-ipv4-special-registry/iana-ipv4-special-registry.xhtml) are correctly detected.

### IPv6
- IPv6 detection is not supported.
- IPv6 lookup support is considered, but not planned.

### API rate limit
- <sup>[2]</sup>The rate calculation is based on laboratory values ​​and is adapted to the real conditions under constant monitoring.

---
All mentioned trademarks are the property of their respective owners.
