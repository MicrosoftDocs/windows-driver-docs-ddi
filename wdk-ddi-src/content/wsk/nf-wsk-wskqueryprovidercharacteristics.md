---
UID: NF:wsk.WskQueryProviderCharacteristics
title: WskQueryProviderCharacteristics function
author: windows-driver-content
description: The WskQueryProviderCharacteristics function queries the range of WSK NPI versions supported by the WSK subsystem.
old-location: netvista\wskqueryprovidercharacteristics.htm
old-project: netvista
ms.assetid: b8a81d7e-abab-4343-a044-ac9dd913c7f2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WskQueryProviderCharacteristics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskQueryProviderCharacteristics
req.alt-loc: netio.lib,netio.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Netio.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# WskQueryProviderCharacteristics function



## -description
The 
  <b>WskQueryProviderCharacteristics</b> function queries the range of WSK NPI versions supported by the WSK
  subsystem.



## -syntax

````
NTSTATUS WskQueryProviderCharacteristics(
  _In_  PWSK_REGISTRATION             WskRegistration,
  _Out_ PWSK_PROVIDER_CHARACTERISTICS WskProviderCharacteristics
);
````


## -parameters

### -param WskRegistration [in]

A pointer to the memory location initialized by 
     <a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a> that identifies a WSK
     application's registration instance.


### -param WskProviderCharacteristics [out]

A pointer to the range of WSK NPI versions supported by the WSK subsystem.


## -returns
<b>WskQueryProviderCharacteristics</b> returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The query completed successfully.
<dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl>The provider NPI was not yet available.
<dl>
<dt><b>Other status codes</b></dt>
</dl>The query failed.

 


## -remarks
WSK clients can use this function to determine the WSK NPI versions supported by the WSK
    subsystem.


## -see-also
<dl>
<dt>
<a href="..\wsk\ns-wsk-_wsk_provider_characteristics.md">WSK_PROVIDER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_registration.md">WSK_REGISTRATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WskQueryProviderCharacteristics function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

