---
UID: NS:windot11._DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS
title: "_DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS"
author: windows-driver-content
description: the DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS structure is returned in a NDIS_STATUS_DOT11_WFD_DISCOVER_COMPLETE indication.
old-location: netvista\_dot11_wfd_discover_complete_parameters.htm
tech.root: netvista
ms.assetid: 0CAB1436-357F-4F9F-98F8-F05B3D86B00A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, PDOT11_WFD_DISCOVER_COMPLETE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, netvista._dot11_wfd_discover_complete_parameters, windot11/ DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, windot11/PDOT11_WFD_DISCOVER_COMPLETE_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
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
req.lib:
req.dll:
req.irql:
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Windot11.h
api_name:
-	DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, *PDOT11_WFD_DISCOVER_COMPLETE_PARAMETERS
product:
- Windows 10 or later.
---

# _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>the <b>DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS</b> structure is returned in a  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451704">NDIS_STATUS_DOT11_WFD_DISCOVER_COMPLETE</a> indication. The structure contains a list of devices discovered


## -syntax


````
typedef struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  NDIS_STATUS        Status;
  ULONG              uNumOfEntries;
  ULONG              uTotalNumOfEntries;
  ULONG              uListOffset;
  ULONG              uListLength;
} DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, *PDOT11_WFD_DISCOVER_COMPLETE_PARAMETERS;
````


## -struct-fields




### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following:

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_DISCOVER_COMPLETE_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field Status

The appropriate status code for the device discovery operation. If this value is not <b>NDIS_STATUS_SUCCESS</b>, the rest of the members in this structure must be set to 0.


### -field uNumOfEntries

The total number of discovered devices in the list at <b>uListOffset</b>. The number of entries cannot exceed <b>DOT11_WFD_DISCOVER_COMPLETE_MAX_LIST_SIZE</b>.


### -field uTotalNumOfEntries

The total number of discovered devices in actually discovered  by the driver. The number of entries cannot exceed <b>DOT11_WFD_DISCOVER_COMPLETE_MAX_LIST_SIZE</b>.


### -field uListOffset

The offset in the <b>StatusBuffer</b> of <a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a> where the list of <a href="..\windot11\ns-windot11-_dot11_wfd_device_entry.md">DOT11_WFD_DEVICE_ENTRY</a> elements begins.


### -field uListLength

The length, in bytes of the device list at <b>uListOffset</b>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451704">NDIS_STATUS_DOT11_WFD_DISCOVER_COMPLETE</a>



 

 


