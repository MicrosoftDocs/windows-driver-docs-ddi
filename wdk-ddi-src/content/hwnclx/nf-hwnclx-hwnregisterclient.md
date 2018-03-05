---
UID: NF:hwnclx.HwNRegisterClient
title: HwNRegisterClient function
author: windows-driver-content
description: Registers the hardware notification client driver and its callback functions with the class extension.
old-location: gpiobtn\hwnregisterclient.htm
old-project: gpiobtn
ms.assetid: 69de1551-e41f-4d18-89db-28d190676922
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: HwNRegisterClient, HwNRegisterClient function, gpiobtn.hwnregisterclient, hwnclx/HwNRegisterClient
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hwnclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.lib: Mshwnclxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Mshwnclxstub.lib
-	Mshwnclxstub.dll
api_name:
-	HwNRegisterClient
product: Windows
targetos: Windows
req.typenames: HWN_CLX_EXPORT_INDEX, *PHWN_CLX_EXPORT_INDEX
---

# HwNRegisterClient function


## -description


Registers the hardware notification client driver and its callback functions with the class extension. This function should be invoked when the client driver is loaded and the <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine is called for initialization. F


## -syntax


````
FORCEINLINE NTSTATUS  HwNRegisterClient(
  _In_    WDFDRIVER                        Driver,
  _Inout_ PHWN_CLIENT_REGISTRATION_PACKET  RegistrationPacket,
  _In_    PUNICODE_STRING                  RegistryPath
);
````


## -parameters




### -param Driver [in]

Handle to the client drivers framework driver object. 


### -param RegistrationPacket [in, out]

Pointer to the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> structure that contains function pointers to the callback functions defined in the client driver implementation and required by the class extension.


### -param RegistryPath [in]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the path to the client driver’s registry key. 


## -returns



Returns STATUS_SUCCESS if function succeeds. Returns STATUS_INVALID_PARAMETER if corresponding client driver can't be found. Otherwise, it returns one of the error status values defined in Ntstatus.h.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a>



<a href="https://msdn.microsoft.com/405ff6db-9bc0-42f3-a740-49dd3967a8b3">Hardware notifications reference</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [gpiobtn\gpiobtn]:%20HwNRegisterClient function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

