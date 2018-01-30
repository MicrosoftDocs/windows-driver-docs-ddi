---
UID: NF:dot11wdi.NdisMRegisterWdiMiniportDriver
title: NdisMRegisterWdiMiniportDriver function
author: windows-driver-content
description: A miniport driver calls the NdisMRegisterWdiMiniportDriver function to register MiniportWdiXxx entry points with NDIS as the first step in initialization.
old-location: netvista\ndismregisterwdiminiportdriver.htm
old-project: netvista
ms.assetid: 60FE4E6C-38D4-438F-983B-7336926F6FE2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndismregisterwdiminiportdriver, NdisMRegisterWdiMiniportDriver function [Network Drivers Starting with Windows Vista], NdisMRegisterWdiMiniportDriver, dot11wdi/NdisMRegisterWdiMiniportDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMRegisterWdiMiniportDriver
product: Windows
targetos: Windows
req.typenames: WDI_TX_PAUSE_REASON
---

# NdisMRegisterWdiMiniportDriver function


## -description


A miniport driver calls the NdisMRegisterWdiMiniportDriver function to register MiniportWdiXxx entry points with NDIS as the first step in initialization.


## -syntax


````
NDIS_STATUS NdisMRegisterWdiMiniportDriver(
  _In_     DRIVER_OBJECT                            *DriverObject,
  _In_     PCUNICODE_STRING                         RegistryPath,
  _In_opt_ NDIS_MINIPORT_DRIVER_CONTEXT             NdisDriverContext,
  _In_     NDIS_MINIPORT_DRIVER_CHARACTERISTICS     *MiniportDriverCharacteristics,
  _In_     NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS *MiniportWdiCharacteristics,
  _Out_    NDIS_MINIPORT_DRIVER_HANDLE              *NdisMiniportDriverHandle
);
````


## -parameters




### -param DriverObject [in]

A pointer to an opaque driver object that the miniport driver received in its 
     <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine at the 
     <i>Argument1</i> parameter (see 
     <mshelp:link keywords="netvista.driverentry_of_ndis_miniport_drivers" tabindex="0"><b>DriverEntry of NDIS
     Miniport Drivers</b></mshelp:link>).


### -param RegistryPath [in]

A pointer to an opaque registry path that the miniport driver received in its 
     <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine at the 
     <i>Argument2</i> parameter.


### -param NdisDriverContext [in, optional]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information.


### -param MiniportDriverCharacteristics [in]

A pointer to an 
     <mshelp:link keywords="netvista.ndis_miniport_driver_characteristics" tabindex="0"><b>
     NDIS_MINIPORT_DRIVER_CHARACTERISTICS</b></mshelp:link> structure that the caller initialized.


### -param MiniportWdiCharacteristics [in]

A pointer to an 
     
     <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a> structure that the caller initialized.


### -param NdisMiniportDriverHandle [out]

A pointer to a caller-supplied handle variable. NDIS writes a handle to this variable that
     uniquely identifies this driver. The driver must save this handle for use in subsequent 
     <b>Ndis<i>Xxx</i></b> function calls.


## -returns



            NdisMRegisterWdiMiniportDriver can return any of the following return values.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NdisMRegisterWdiMiniportDriver registered the WDI miniport driver successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>
</td>
<td width="60%">
The 
       <i>CharacteristicsLength</i> parameter is incorrect for the NDIS version that is specified at the 
       <b>MajorNdisVersion</b> member in the structure at 
       <i>MiniportDriverCharacteristics</i> .

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
The 
       <b>MajorNdisVersion</b> or 
       <b>MinorNdisVersion</b> specified in the characteristics structure is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A shortage of resources, possibly memory, prevented NDIS from registering the caller.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
This is a default error status, returned when none of the preceding errors caused the
       registration to fail.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other NDIS_STATUS codes</b></dt>
</dl>
</td>
<td width="60%">
An appropriate NDIS_STATUS code in the case of a failure.

</td>
</tr>
</table> 



## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_driver_characteristics.md">NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a>

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMRegisterWdiMiniportDriver function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

