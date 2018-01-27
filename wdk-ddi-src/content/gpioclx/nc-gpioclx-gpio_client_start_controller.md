---
UID: NC:gpioclx.GPIO_CLIENT_START_CONTROLLER
title: GPIO_CLIENT_START_CONTROLLER
author: windows-driver-content
description: The CLIENT_StartController event callback function performs operations that are needed when the general-purpose I/O (GPIO) controller device enters the D0 power state.
old-location: gpio\client_startcontroller.htm
old-project: GPIO
ms.assetid: 311C5273-1C16-4EA7-96B4-838CCE6926BA
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.client_startcontroller, CLIENT_StartController callback function [Parallel Ports], CLIENT_StartController, GPIO_CLIENT_START_CONTROLLER, GPIO_CLIENT_START_CONTROLLER, gpioclx/CLIENT_StartController
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: Called at PASSIVE_LEVEL (see Remarks).
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Gpioclx.h
apiname: 
-	CLIENT_StartController
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---

# GPIO_CLIENT_START_CONTROLLER callback


## -description


The <i>CLIENT_StartController</i> event callback function performs operations that are needed when the general-purpose I/O (GPIO) controller device enters the D0 power state.


## -prototype


````
GPIO_CLIENT_START_CONTROLLER CLIENT_StartController;

NTSTATUS CLIENT_StartController(
  _In_ PVOID                  Context,
  _In_ BOOLEAN                RestoreContext,
  _In_ WDF_POWER_DEVICE_STATE PreviousPowerState
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param RestoreContext [in]

Whether the client driver should restore the GPIO controller to a previously saved hardware context. If TRUE, the hardware context should be restored. If FALSE, the hardware context should not be restored. For more information, see Remarks.


### -param PreviousPowerState [in]

The previous device power state. This parameter is a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_power_device_state.md">WDF_POWER_DEVICE_STATE</a> enumeration value that specifies the low-power state from which the device entered the D0 power state. The GPIO controller driver can use this information to determine how to configure the controller device so that it is ready to use.


## -returns


The <i>CLIENT_StartController</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.



## -remarks


This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to place the GPIO controller device in a known, initial state at system startup or when the device transitions from a low-power state to a working state. This callback function must perform any operations that are necessary after the device wakes from a low-power state, such as restoring any information that the driver needs after the device enters the D0 power state.

Typically, a <i>CLIENT_StartController</i> callback function sets all the GPIO pins to their default state.

To register your driver's <i>CLIENT_StartController</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_StartController</i> function pointer.

Although the <i>CLIENT_StartController</i> callback function is called at IRQL = PASSIVE_LEVEL, you should not make this function <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>. The <i>CLIENT_StartController</i> callback is in the critical timing path for restoring power to the devices in the hardware platform and, for performance reasons, it should not be delayed by page faults.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_StartController callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

