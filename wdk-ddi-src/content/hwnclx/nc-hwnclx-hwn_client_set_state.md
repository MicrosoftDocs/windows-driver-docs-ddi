---
UID: NC:hwnclx.HWN_CLIENT_SET_STATE
title: HWN_CLIENT_SET_STATE
author: windows-driver-content
description: Implemented by the client driver to set hardware notification component state. It is invoked when a user wants to change the state of a driver.
old-location: gpiobtn\hwn_client_set_state.htm
old-project: gpiobtn
ms.assetid: 5d2ccc29-4022-467c-9f37-d49badcceba4
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PHWN_CLIENT_SET_STATE, *PHWN_CLIENT_SET_STATE callback function pointer, HWN_CLIENT_SET_STATE, HwnClientSetState, HwnClientSetState callback function, gpiobtn.hwn_client_set_state, hwnclx/HwnClientSetState"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Hwnclx.h
api_name:
-	*PHWN_CLIENT_SET_STATE
product: Windows
targetos: Windows
req.typenames: HPMI_QUERY_CAPABILITIES_RESPONSE, *PHPMI_QUERY_CAPABILITIES_RESPONSE
---

# HWN_CLIENT_SET_STATE callback


## -description



Implemented by the client driver to set hardware notification component state. It is invoked when a user wants to change the state of a driver.


## -prototype


````
HWN_CLIENT_SET_STATE HwnClientSetState;

NTSTATUS HwnClientSetState(
  _In_  PVOID  Context,
  _In_  PVOID  Buffer,
  _In_  ULONG  BufferLength,
  _Out_ PULONG BytesWritten
)
{ ... }

typedef HWN_CLIENT_SET_STATE *PHWN_CLIENT_SET_STATE;
````


## -parameters




### -param Context [in]

Pointer to the client driver's context information. This memory space is available for use by the client driver. It is allocated as part of the framework object context space by <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.


### -param Buffer [in]

Buffer of <i>BufferLength</i> bytes containing a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_HEADER</a> structure including one or more <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_SETTINGS</a> structures that specify the hardware notifications to be set.


### -param BufferLength [in]

The size of <i>Buffer</i> in bytes.


### -param BytesWritten [out]

Pointer to a variable that indicates the number of bytes written by the function.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.




## -remarks



Register your implementation of this callback function by setting the appropriate member of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and then calling <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a>.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a>



<a href="https://msdn.microsoft.com/405ff6db-9bc0-42f3-a740-49dd3967a8b3">Hardware notifications reference</a>



 

 


