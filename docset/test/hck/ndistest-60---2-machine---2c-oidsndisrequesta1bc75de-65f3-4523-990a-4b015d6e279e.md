---
author: joshbax-msft
title: NDISTest 6.0 - 2 Machine - 2c\_OidsNdisRequest
description: NDISTest 6.0 - 2 Machine - 2c\_OidsNdisRequest
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: efc770da-0eda-4eef-87c5-2c29345629a8
---

# NDISTest 6.0 - 2 Machine - 2c\_OidsNdisRequest


This test performs a series of NdisRequest calls to the driver to verify that it supports the querying of all required information OIDS. It will query OID\_GEN\_SUPPORTED\_OIDS, verify that all required OIDs are present, and then query them.

The NDIS Test is not able to verify the values returned by most of these OIDs.

It also checks that the requests modify the fields of the NDIS\_REQUEST structure correctly for both queries and sets: It verifies the byteswritten/bytesread field equal the bytes required by the OID, and checks that the buffer is not inappropriately modified.

You should check the log carefully for problems.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Network.LAN.Base.NDISRequirements</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows 7 (x64) Windows 7 (x86) Windows 8 (x64) Windows 8 (x86) Windows Server 2012 (x64) Windows Server 2008 R2 (x64) Windows 8.1 x64 Windows 8.1 x86 Windows Server 2012 R2</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~5 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification Functional</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [LAN Testing Prerequisites](lan-testing-prerequisites.md).

## Troubleshooting


For troubleshooting information, see [Troubleshooting LAN Testing](troubleshooting-lan-testing.md).

## More information


### Parameters

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
<td><p>queryTestDeviceID</p></td>
<td><p>The ID of the test device.</p>
<p>Example: //Devnode/DeviceID</p></td>
</tr>
<tr class="even">
<td><p>SupportDeviceGuid0</p></td>
<td><p>The support device GUID.</p></td>
</tr>
<tr class="odd">
<td><p>ClientMessageDeviceGuid</p></td>
<td><p>The client message device GUID.</p></td>
</tr>
<tr class="even">
<td><p>ServerMessageDeviceGuid</p></td>
<td><p>The server message device GUID.</p></td>
</tr>
</tbody>
</table>

 

### Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>[WTTRunWorkingDir]\ndistest\bin\ndtest.exe /logo /auto /server /support:[SupportDeviceGuid0] /msg:[ServerMessageDeviceGuid]</strong></p></td>
<td><p>Runs the NDIS test server.</p></td>
</tr>
<tr class="even">
<td><p><strong>[WTTRunWorkingDir]\ndistest\bin\ndtest.exe /auto /client /dvi /u /target:Miniport /tc:[queryTestDeviceID] /support:[SupportDeviceGuid0] /msg:[ClientMessageDeviceGuid] /script:{2c_OidsNdisRequest.wsf}</strong></p></td>
<td><p>Runs the NDIS test client.</p></td>
</tr>
</tbody>
</table>

 

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_hck\p_hck%5D:%20NDISTest%206.0%20-%202%20Machine%20-%202c_OidsNdisRequest%20%20RELEASE:%20%284/27/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



