---
author: joshbax-msft
title: WiFi Direct Scenario Tests - Airplane Mode
description: WiFi Direct Scenario Tests - Airplane Mode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ed39b951-ee97-483d-afa6-1bf7018508b8
---

# WiFi Direct Scenario Tests - Airplane Mode


This test suite verifies Wi-Fi Direct (WFD) behavior when the device under test (DUT) is toggled between AirplaneMode on and off. These tests apply to Always On Always Connected (AOAC) and non-AOAC systems.

The tests confirm that the following statements are true:

1.  Autonomous Group Owner (GO) is dismantled in AirplaneMode and stays dismantled on NormalMode.

2.  System discoverability is turned off in AirplaneMode and stays off on NormalMode.

3.  WFD connection is dismantled in AirplaneMode and stays dismantled on NormalMode.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Network.WLAN.CSBWiFiDirect.SupportAtLeast2WiFiDirectPortsConcurrently Device.Network.WLAN.CSBWiFiDirect.SupportAtLeast4Clients Device.Network.WLAN.WiFiDirect.SupportAtLeast2WiFiDirectPortsConcurrently Device.Network.WLAN.WiFiDirect.SupportAtLeast4Clients</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows RT (ARM-based) Windows 8 (x64) Windows 8 (x86) Windows RT 8.1 Windows 8.1 x64 Windows 8.1 x86</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~20 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification Reliability</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [Wireless LAN (802.11) Testing Prerequisites](wireless-lan--80211--testing-prerequisites.md).

Successful tests run as follows:

1.  The device under test (DUT) starts an Autonomous GO.

    1.  The system under test (SUT) scans and finds the GO.

    2.  The DUT is put into AirplaneMode.

    3.  The SUT scans and does not find the GO.

    4.  The DUT is put into NormalMode and verifies that its GO is not running.

    5.  The SUT scans and does not find the GO.

2.  The DUT is set to the listen state (discoverable).

    1.  The SUT starts a discover request and finds the DUT.

    2.  The DUT is put into AirplaneMode.

    3.  The SUT starts a discover request and does not find the DUT.

    4.  The DUT is put into NormalMode and verifies that its listen state is turned off.

    5.  The SUT starts a discover request and does not find the DUT.

3.  WFD pairing occurs between the DUT and the SUT.

    1.  The DUT is put into AirplaneMode.

    2.  The SUT receives a disconnect notification.

    3.  The DUT is put into NormalMode and confirms that it has no active sessions.

## Troubleshooting


For troubleshooting information, see [Troubleshooting Wireless LAN (802.11) Tests](troubleshooting-wireless-lan--80211--tests.md).

## More information


### Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PIN</strong></p></td>
<td><p>The WPS PIN for WFD pairing.</p>
<p>Default Value: 12345670</p></td>
</tr>
</tbody>
</table>

 

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_hck\p_hck%5D:%20WiFi%20Direct%20Scenario%20Tests%20-%20Airplane%20Mode%20%20RELEASE:%20%284/27/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



