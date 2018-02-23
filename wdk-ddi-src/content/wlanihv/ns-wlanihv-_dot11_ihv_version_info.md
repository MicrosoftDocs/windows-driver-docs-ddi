---
UID: NS:wlanihv._DOT11_IHV_VERSION_INFO
title: "_DOT11_IHV_VERSION_INFO"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_ihv_version_info.htm
old-project: netvista
ms.assetid: d482abdc-c6c1-4789-a1fc-39e76c32e78a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11_IHV_VERSION_INFO, PDOT11_IHV_VERSION_INFO, netvista.dot11_ihv_version_info, wlanihv/PDOT11_IHV_VERSION_INFO, Native_802.11_data_types_65cab8b1-5ff7-4775-a3e9-b93e161e6bd3.xml, _DOT11_IHV_VERSION_INFO, *PDOT11_IHV_VERSION_INFO, wlanihv/DOT11_IHV_VERSION_INFO, PDOT11_IHV_VERSION_INFO structure pointer [Network Drivers Starting with Windows Vista], DOT11_IHV_VERSION_INFO structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wlanihv.h
apiname:
-	DOT11_IHV_VERSION_INFO
product: Windows
targetos: Windows
req.typenames: DOT11_IHV_VERSION_INFO, *PDOT11_IHV_VERSION_INFO
req.product: Windows 10 or later.
---

# _DOT11_IHV_VERSION_INFO structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_IHV_VERSION_INFO structure defines the versions of the IHV Extensibility functions that are
  supported by the IHV Extensions DLL.


## -syntax


````
typedef struct _DOT11_IHV_VERSION_INFO {
  DWORD dwVerMin;
  DWORD dwVerMax;
} DOT11_IHV_VERSION_INFO, *PDOT11_IHV_VERSION_INFO;
````


## -struct-fields




### -field dwVerMin

The minimum API version supported by the IHV Extensions DLL.
     

For the Windows Vista operating system, the minimum API version is zero.


### -field dwVerMax

The maximum API version supported by the IHV Extensions DLL.
     

For the Windows Vista operating system, the maximum API version is zero.


## -remarks



Prior to starting the IHV Extensions DLL through a call to the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a> IHV
    handler function, the operating system queries the API versions supported by the IHV Extensions DLL
    through a call to the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_get_version_info.md">Dot11ExtIhvGetVersionInfo</a> IHV
    handler function. The IHV Extensions DLL returns the range of API versions it supports through the 
    <i>pDot11IHVVersionInfo</i> parameter.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_service.md">Dot11ExtIhvInitService</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_get_version_info.md">Dot11ExtIhvGetVersionInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_IHV_VERSION_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

