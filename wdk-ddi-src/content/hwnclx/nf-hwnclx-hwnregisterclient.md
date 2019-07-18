---
UID: NF:hwnclx.HwNRegisterClient
title: HwNRegisterClient function (hwnclx.h)
description: Registers the hardware notification client driver and its callback functions with the class extension.
old-location: gpiobtn\hwnregisterclient.htm
tech.root: gpiobtn
ms.assetid: 69de1551-e41f-4d18-89db-28d190676922
ms.date: 02/15/2018
ms.keywords: HwNRegisterClient, HwNRegisterClient function, gpiobtn.hwnregisterclient, hwnclx/HwNRegisterClient
ms.topic: function
f1_keywords:
 - "hwnclx/HwNRegisterClient"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Mshwnclxstub.lib
- Mshwnclxstub.dll
api_name:
- HwNRegisterClient
product:
- Windows
targetos: Windows
req.typenames: HWN_CLX_EXPORT_INDEX, *PHWN_CLX_EXPORT_INDEX
---

# HwNRegisterClient function


## -description


Registers the hardware notification client driver and its callback functions with the class extension. This function should be invoked when the client driver is loaded and the <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine is called for initialization. F


## -syntax


```cpp
FORCEINLINE NTSTATUS  HwNRegisterClient(
  _In_    WDFDRIVER                        Driver,
  _Inout_ PHWN_CLIENT_REGISTRATION_PACKET  RegistrationPacket,
  _In_    PUNICODE_STRING                  RegistryPath
);
```


## -parameters




### -param Driver [in]

Handle to the client drivers framework driver object.


### -param RegistrationPacket [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> structure that contains function pointers to the callback functions defined in the client driver implementation and required by the class extension.


### -param RegistryPath [in]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the path to the client driver’s registry key.


## -returns



Returns STATUS_SUCCESS if function succeeds. Returns STATUS_INVALID_PARAMETER if corresponding client driver can't be found. Otherwise, it returns one of the error status values defined in Ntstatus.h.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Hardware notifications reference</a>



 

 


