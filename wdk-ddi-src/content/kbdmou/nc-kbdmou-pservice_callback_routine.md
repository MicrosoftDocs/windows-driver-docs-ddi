---
UID: NC:kbdmou.PSERVICE_CALLBACK_ROUTINE
title: PSERVICE_CALLBACK_ROUTINE
author: windows-driver-content
description: A function driver calls the class service callback in its ISR dispatch completion routine. The class service callback transfers input data from the input data buffer of a device to the class data queue.
old-location: hid\kbdclass_class_service_callback_routine.htm
tech.root: hid
ms.assetid: 78ae2a98-bebd-43ee-b016-2f619c3135ca
ms.date: 04/30/2018
ms.keywords: ClassServiceCallback, ClassServiceCallback callback function [Human Input Devices], PSERVICE_CALLBACK_ROUTINE, PSERVICE_CALLBACK_ROUTINE callback, hid.kbdclass_class_service_callback_routine, kbdmou/ClassServiceCallback, kref_c3fa9125-0bc4-4936-b4e5-eb4e5eee23e2.xml
ms.topic: callback
req.header: kbdmou.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	kbdmou.h
api_name:
-	ClassServiceCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSERVICE_CALLBACK_ROUTINE callback function


## -description


A function driver calls the class service callback in its ISR dispatch completion routine. The class service callback transfers input data from the input data buffer of a device to the class data queue. 


## -parameters




### -param NormalContext [in]

Pointer to the class device object.


### -param SystemArgument1 [in]

Pointer to the first keyboard input data packet in the input data buffer of the port device.


### -param SystemArgument2 [in]

Pointer to the keyboard input data packet that immediately follows the last data packet in the input data buffer of the port device.


### -param SystemArgument3 [in, out]

Pointer to the number of keyboard input data packets that are transferred by the routine.


## -returns



This callback function does not return a value.




## -remarks



<b>Keyboard Class Service Callback</b>

Here is the definition of the  keyboard class service callback routine.

Kbdclass uses an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541273">IOCTL_INTERNAL_KEYBOARD_CONNECT</a> request to connect its class service callback to a keyboard device. In this call, the driver sets  its implementation in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538370">CONNECT_DATA</a> structure.

<pre class="syntax" xml:space="preserve"><code>
/*
DeviceObject [in] 
Pointer to the class device object.

InputDataStart [in] 
Pointer to the first keyboard input data packet in the input data buffer of the port device.

InputDataEnd [in] 
Pointer to the keyboard input data packet that immediately follows the last data packet in the input data buffer of the port device.

InputDataConsumed [in, out] 
Pointer to the number of keyboard input data packets that are transferred by the routine.

*/
VOID KeyboardClassServiceCallback(
  _In_    PDEVICE_OBJECT       DeviceObject,
  _In_    PKEYBOARD_INPUT_DATA InputDataStart,
  _In_    PKEYBOARD_INPUT_DATA InputDataEnd,
  _Inout_ PULONG               InputDataConsumed
);
</code></pre>
<b>KeyboardClassServiceCallback</b> transfers input data from the input buffer of the device to the class data queue. This routine is called by the ISR dispatch completion routine of the function driver.

<b>KeyboardClassServiceCallback</b> can be supplemented by a filter service callback that is provided by an upper-level keyboard filter driver. A filter service callback filters the keyboard data that is transferred to the class data queue. For example, the filter service callback can delete, transform, or insert data. <a href="http://go.microsoft.com/fwlink/p/?linkid=256125">Kbfiltr</a>, the sample filter driver in code gallery, includes <b>KbFilter_ServiceCallback</b>, which is a template for a keyboard filter service callback.

<b>Mouse Class Service Callback</b>

Here is the <b>MouseClassServiceCallback</b> routine is the class service callback routine that is provided by Mouclass. The driver uses an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541294">IOCTL_INTERNAL_MOUSE_CONNECT</a> request to connect its class service callback to a mouse device. In this call, the driver sets  its implementation in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538370">CONNECT_DATA</a> structure.


<pre class="syntax" xml:space="preserve"><code>
/*
DeviceObject [in] 
Pointer to the class device object.

InputDataStart [in] 
Pointer to the first mouse input data packet in the input buffer of the port device.

InputDataEnd [in] 
Pointer to the mouse input data packet that immediately follows the last data packet in the input data buffer of the port device.

InputDataConsumed [in, out] 
Pointer to the number of mouse input data packets that are transferred by the routine.

*/
VOID MouseClassServiceCallback(
  _In_    PDEVICE_OBJECT    DeviceObject,
  _In_    PMOUSE_INPUT_DATA InputDataStart,
  _In_    PMOUSE_INPUT_DATA InputDataEnd,
  _Inout_ PULONG            InputDataConsumed
);
);
</code></pre>


<b>MouseClassServiceCallback</b> transfers input data from the input buffer of the device to the class data queue. This routine is called by the ISR dispatch completion routine of the function driver.

<b>MouseClassServiceCallback</b> can be supplemented by a filter service callback that is provided by an upper-level mouse filter driver. A filter service callback can filter the mouse data that is transferred to the class data queue. For example, the filter service callback can delete, transform, or insert data. <a href="http://go.microsoft.com/fwlink/p/?linkid=256135">Moufiltr</a>, the sample filter driver in the WDK, includes <b>MouFilter_ServiceCallback</b>, which is a template for a filter service callback.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538370">CONNECT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542337">KEYBOARD_INPUT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542403">MOUSE_INPUT_DATA</a>
 

 

