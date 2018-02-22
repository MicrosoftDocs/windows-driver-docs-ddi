---
UID: NN:wdtf.IWDTFDeviceDepot2
title: IWDTFDeviceDepot2
author: windows-driver-content
description: Defines properties and operations for the collection of devices on a computer.
old-location: dtf\iwdtfdevicedepot2.htm
old-project: dtf
ms.assetid: 7f7f1286-83e9-4bd8-ac57-1c3def4c0035
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dtf.iwdtfdevicedepot2, IWDTFDeviceDepot2 interface [Windows Device Testing Framework], IWDTFDeviceDepot2 interface [Windows Device Testing Framework], described, IWDTFDeviceDepot2, wdtf/IWDTFDeviceDepot2, Microsoft.WDTF.IWDTFDeviceDepot2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: wdtf.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTF.Interop.metadata_dll.dll
apiname:
-	IWDTFDeviceDepot2
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDeviceDepot2 interface


## -description


Defines properties and operations for the collection of devices on a computer.


## -members

The <b>IWDTFDeviceDepot2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406403">Query</a>
</td>
<td align="left" width="63%">
Returns a subset of the devices in the DeviceDepot.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439488">QuerySingle</a>
</td>
<td align="left" width="63%">
Returns a single target device from the DeviceDepot.

</td>
</tr>
</table>Returns a subset of the devices in the DeviceDepot.

Returns a single target device from the DeviceDepot.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFDeviceDepot2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439300">_NewEnum</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the iteration enumerator for the collection of devices in the DeviceDepot.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406342">Count</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the number of devices that are currently provided by the DeviceDepot.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451057">Item</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets an individual device in the DeviceDepot.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406413">RootDevice</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the root device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406421">WDTF</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the main WDTF aggregation object.

</td>
</tr>
</table>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439300">_NewEnum</a>


Read-only

Gets the iteration enumerator for the collection of devices in the DeviceDepot.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh406342">Count</a>


Read-only

Gets the number of devices that are currently provided by the DeviceDepot.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh451057">Item</a>


Read-only

Gets an individual device in the DeviceDepot.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh406413">RootDevice</a>


Read-only

Gets the root device.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh406421">WDTF</a>


Read-only

Gets the main WDTF aggregation object.

 

