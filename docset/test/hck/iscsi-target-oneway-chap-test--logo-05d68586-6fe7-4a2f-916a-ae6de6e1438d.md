---
author: joshbax-msft
title: iSCSI Target Oneway CHAP Test (LOGO)
description: iSCSI Target Oneway CHAP Test (LOGO)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6f6a9680-3169-4e65-b806-148801908c53
---

# iSCSI Target Oneway CHAP Test (LOGO)


This test verifies that the target device (disk, tape, or optical storage device) can use the Challenge Handshake Authentication Protocol (CHAP) authentication mechanism.

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Storage.Hd.Iscsi.BasicFunction</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows 7 (x64) Windows 7 (x86) Windows 8 (x64) Windows 8 (x86) Windows Server 2012 (x64) Windows Server 2008 R2 (x64) Windows Server 2008 x64 Windows Server 2008 x86Windows 8.1 x64Windows 8.1 x86Windows Server 2012 R2</p></td>
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
<td><p>Manual</p></td>
</tr>
</tbody>
</table>

 

## Running the test


Before you run the test, complete the test setup as described in the test requirements: [iSCSI Boot Component Testing Prerequisites](iscsi-boot-component-testing-prerequisites.md).

If this is the first time you are running an iSCSI HBA test, iSCSI Target test, or MPIO test over iSCSI bus type on the HCK client, or if there is no iscsihctconfig.ini under \[HCK Path\]\\JobsWorkingDir\\ on the HCK client, you will receive a dialog box to input iSCSI configuration information and/or HBA information. For more information about this dialog box, see “Running the test” in [iSCSI HBA Boot Test (LOGO)](iscsi-hba-boot-test--logo-ca7ad4d0-6950-4e2d-bdfe-b80c7873ba90.md).

## Troubleshooting


For troubleshooting information, see [Troubleshooting Device.Storage Testing](troubleshooting-devicestorage-testing.md).

In addition:

1.  Look at the job results log file for test failures.

2.  Enter the required data in the configuration dialog box that appears when this job is scheduled. For more information, go to [iSCSI HBA Boot Test (LOGO)](iscsi-hba-boot-test--logo-ca7ad4d0-6950-4e2d-bdfe-b80c7873ba90.md).

This test always return Pass or Fail. To review test details, review the test log from the Windows HCK Manager.

## More information


The test uses multiple variations to verify that a target properly supports one-way CHAP. The first variation performs a logon similar to the user logging in through iSCSI Initiator Control Panel. The rest of the variations perform logon outside of the Microsoft initiator by using the iSCSI protocol. Each variation receives the challenge from the target and responds to the targets with a calculated response. The target is then expected to either continue with the iSCSI logon or return the appropriate status code, depending on the response received.

There are four different variations:

1.  Valid response is returned using hexadecimal encoding

2.  Valid response is returned using base64 encoding

3.  Invalid response is returned using hexadecimal encoding

4.  Invalid response is returned using base64 encoding

To run this test:

1.  Run the test as a Driver Test Manager (DTM) job.

2.  Enter the required data in the configuration dialog box that appears when this job is scheduled

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
<td><p>LogVerbosity</p></td>
<td><p>The verbosity of logging. There are three levels of output: 0, 1, and 2. 2 is the most verbose.</p>
<p>Default value: 1</p></td>
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
<th>Command option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>iscsi_targetchap -oneway –hct –v [LogVerbosity]</strong></p></td>
<td><p>Runs the test.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
For command-line help for this test binary, type **/h**.

 

### File list

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>File</th>
<th>Location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>iscsi_targetchap.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\storage\wdk\iscsi\</p></td>
</tr>
</tbody>
</table>

 

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_hck\p_hck%5D:%20iSCSI%20Target%20Oneway%20CHAP%20Test%20%28LOGO%29%20%20RELEASE:%20%284/27/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



