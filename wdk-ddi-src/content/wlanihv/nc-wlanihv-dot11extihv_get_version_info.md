---
UID: NC:wlanihv.DOT11EXTIHV_GET_VERSION_INFO
title: DOT11EXTIHV_GET_VERSION_INFO
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvgetversioninfo.htm
old-project: netvista
ms.assetid: af75e59d-c4af-43ca-a160-ddc8a7a4a88e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtIhvGetVersionInfo
req.alt-loc: wlanihv.h
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
req.typenames: *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_GET_VERSION_INFO callback



## -description

## -prototype

````
DOT11EXTIHV_GET_VERSION_INFO Dot11ExtIhvGetVersionInfo;

DWORD APIENTRY Dot11ExtIhvGetVersionInfo(
  _Out_ PDOT11_IHV_VERSION_INFO pDot11IHVVersionInfo
)
{ ... }
````


## -parameters

### -param pDot11IHVVersionInfo [out]

A pointer to a 
     <a href="..\wlanihv\ns-wlanihv-_dot11_ihv_version_info.md">DOT11_IHV_VERSION_INFO</a> structure,
     which contains the interface version numbers.


## -returns
If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.


## -remarks
The operating system calls the 
    <i>Dot11ExtIhvGetVersionInfo</i> function to determine what version of the interface to use with the IHV
    Extension DLL. The operating system makes this call immediately after loading the DLL, and this call is
    the first that the operating system makes into the DLL.

Unlike other IHV Extensibility and Handler functions, whose addresses are resolved through a table of
    function pointers that are exchanged through a call to 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a>, the
    address of the 
    <i>Dot11ExtIhvGetVersionInfo</i> function is resolved by the operating system by the operating system
    calling the 
    <b>GetProcAddress</b> function. As a result, the developer of the IHV Extensions DLL must follow these
    guidelines.

The DLL must implement a function named Dot11ExtIhvGetVersionInfo, which has the format that is
      described in this topic.

The 
      <b>EXPORTS</b> statement of the source module-definition (.def) file, which is used to build the IHV
      Extensions DLL, must contain a function name entry for the 
      <i>Dot11ExtIhvGetVersionInfo</i> function.

For more information about 
    <b>GetProcAddress</b>, refer to the Microsoft Windows SDK documentation.


## -see-also
<dl>
<dt>
<a href="..\wlanihv\ns-wlanihv-_dot11_ihv_version_info.md">DOT11_IHV_VERSION_INFO</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_GET_VERSION_INFO callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

