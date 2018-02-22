---
UID: NF:storport.StorPortSetAdapterBusType
title: StorPortSetAdapterBusType function
author: windows-driver-content
description: Used to adjust the BusType of the adapter depending on its current configuration.
old-location: storage\storportsetadapterbustype.htm
old-project: storage
ms.assetid: 818A9F03-F56E-47D6-A9D1-DD0F63B05054
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: StorPortSetAdapterBusType, StorPortSetAdapterBusType routine [Storage Devices], storport/StorPortSetAdapterBusType, storage.storportsetadapterbustype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortSetAdapterBusType
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortSetAdapterBusType function


## -description


Used to adjust the BusType of the adapter depending on its current configuration. Setting the BusType with this routine will allow you to override the global property set in the miniport INF without having to re-install the driver. This is useful for scenarios such as RAID support or support for multiple adapters with a different bus type.


## -syntax


````
ULONG StorPortSetAdapterBusType(
  _In_ PVOID HwDeviceExtension,
  _In_ ULONG BusType
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.


### -param BusType [in]

Contains a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff566356">STORAGE_BUS_TYPE</a> that specifies the type of bus-specific configuration data to be set.


## -returns



The <b>StorPortSetAdapterBusType</b> routine returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
This routine will return this value if it was called outside the <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> function.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
This routine will return this value if it was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This routine fails with this return value if the BusType is an invalid value.

</td>
</tr>
</table>
 



