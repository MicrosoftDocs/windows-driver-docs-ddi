---
UID: NF:ndis.NdisIMCancelInitializeDeviceInstance
title: NdisIMCancelInitializeDeviceInstance function
author: windows-driver-content
description: The NdisIMCancelInitializeDeviceInstance function cancels a preceding call to the NdisIMInitializeDeviceInstanceEx function.
old-location: netvista\ndisimcancelinitializedeviceinstance.htm
old-project: netvista
ms.assetid: 809ffee1-b087-4bf0-ba8a-1ac0b2d02f2f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: intermediate_ref_4cdce462-8c79-46ad-aa3e-68a0f9b72ef1.xml, NdisIMCancelInitializeDeviceInstance, NdisIMCancelInitializeDeviceInstance function [Network Drivers Starting with Windows Vista], ndis/NdisIMCancelInitializeDeviceInstance, netvista.ndisimcancelinitializedeviceinstance
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisIMCancelInitializeDeviceInstance (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers   (see       NdisIMCancelInitializeDeviceInstance (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_IM_Function
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
-	NdisIMCancelInitializeDeviceInstance
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisIMCancelInitializeDeviceInstance function


## -description


The 
  <b>NdisIMCancelInitializeDeviceInstance</b> function cancels a preceding call to the 
  <mshelp:link keywords="netvista.ndisiminitializedeviceinstanceex" tabindex="0"><b>
  NdisIMInitializeDeviceInstanceEx</b></mshelp:link> function.


## -syntax


````
NDIS_STATUS NdisIMCancelInitializeDeviceInstance(
  _In_ NDIS_HANDLE  DriverHandle,
  _In_ PNDIS_STRING DeviceInstance
);
````


## -parameters




#### - DriverHandle [in]

The miniport driver handle that the 
     <mshelp:link keywords="netvista.ndismregisterminiportdriver" tabindex="0"><b>
     NdisMRegisterMiniportDriver</b></mshelp:link> function returned at the 
     <i>NdisMiniportDriverHandle</i> parameter.


#### - DeviceInstance [in]

A pointer to an NDIS_STRING type that describes a caller-initialized counted string in the
     system-default character set. The string contains the name of the registry key in which the driver
     stores information about a virtual miniport and, possibly, binding-specific information. For Microsoft
     Windows 2000 and later drivers, this string contains Unicode characters. That is, for Windows 2000 and
     later, NDIS defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


## -returns


<b>NdisIMCancelInitializeDeviceInstance</b> returns NDIS_STATUS_SUCCESS if it canceled the preceding call
     to 
     <b>NdisIMInitializeDeviceInstanceEx</b>. Otherwise, it returns NDIS_STATUS_FAILURE if there is no way to
     stop the initialization operation for the virtual miniport.



## -remarks


An intermediate driver calls the 
    <mshelp:link keywords="netvista.ndisiminitializedeviceinstanceex" tabindex="0"><b>
    NdisIMInitializeDeviceInstanceEx</b></mshelp:link> function to initiate the initialization operation for a virtual
    miniports.Before NDIS calls the driver's 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function, the
    driver can call 
    <b>NdisIMCancelInitializeDeviceInstance</b> to cancel the initialization operation. For example, if an
    underlying driver that the intermediate driver requires for normal operation is removed, the intermediate
    driver can cancel the initialization for any virtual miniports that are associated with the removed
    driver.



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<mshelp:link keywords="netvista.ndisiminitializedeviceinstanceex" tabindex="0"><b>
   NdisIMInitializeDeviceInstanceEx</b></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIMCancelInitializeDeviceInstance function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

