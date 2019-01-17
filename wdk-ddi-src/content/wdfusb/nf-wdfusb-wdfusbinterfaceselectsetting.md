---
UID: NF:wdfusb.WdfUsbInterfaceSelectSetting
title: WdfUsbInterfaceSelectSetting function
description: The WdfUsbInterfaceSelectSetting method selects a specified alternate setting for a specified USB interface.
old-location: wdf\wdfusbinterfaceselectsetting.htm
tech.root: wdf
ms.assetid: 398b7649-152e-4fed-b633-16627dadf0f8
ms.date: 02/26/2018
ms.keywords: DFUsbRef_256e9b5d-8e9b-4935-9dc9-38a6071258a6.xml, WdfUsbInterfaceSelectSetting, WdfUsbInterfaceSelectSetting method, kmdf.wdfusbinterfaceselectsetting, wdf.wdfusbinterfaceselectsetting, wdfusb/WdfUsbInterfaceSelectSetting
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbInterfaceSelectSetting
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbInterfaceSelectSetting function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceSelectSetting</b> method selects a specified alternate setting for a specified USB interface.


## -parameters




### -param UsbInterface [in]

A handle to a USB interface object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550092">WdfUsbTargetDeviceGetInterface</a>. 


### -param PipesAttributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for pipe objects that the framework creates for the interface. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Params [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure that contains interface selection parameters.


## -returns



<b>WdfUsbInterfaceSelectSetting</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to create a new pipe object.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfUsbInterfaceSelectSetting</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After your driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550101">WdfUsbTargetDeviceSelectConfig</a> to select a configuration, the driver can call <b>WdfUsbInterfaceSelectSetting</b> to select an alternate setting for one of the device's interfaces.

Your driver can select an interface's alternate setting by specifying a USB interface descriptor or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>, or by just providing an alternate setting for the interface. In all cases, the driver must provide a handle to an interface object. 

If your driver just provides an alternate setting, the framework uses the interface object to determine the interface to which the setting belongs. 

If your driver specifies an interface descriptor or a URB, the framework uses the interface that is specified in the descriptor or URB.

The framework creates a framework USB pipe object for each pipe that is associated with the interface, after deleting any pipe objects that the framework might have previously created for the interface. To obtain information about an interface's pipe objects, your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550066">WdfUsbInterfaceGetNumConfiguredPipes</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>.

For more information about the <b>WdfUsbInterfaceSelectSetting</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure with attributes for the pipe objects that the framework will create. Then, the example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure to specify alternate setting 1. Finally, the example calls <b>WdfUsbInterfaceSelectSetting</b> to select the alternate setting and create pipe objects for the interface's pipes.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  pipesAttributes;
WDF_USB_INTERFACE_SELECT_SETTING_PARAMS  selectSettingParams;
NTSTATUS  Status;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;pipesAttributes);
WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE(
                                       &amp;pipesAttributes,
                                       MY_PIPE_CONTEXT
                                       );

WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING(
                                      &amp;selectSettingParams,
                                      1
                                      );

Status = WdfUsbInterfaceSelectSetting(
                                      UsbInterface,
                                      &amp;pipesAttributes,
                                      &amp;selectSettingParams
                                      );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553003">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553011">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550066">WdfUsbInterfaceGetNumConfiguredPipes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550092">WdfUsbTargetDeviceGetInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550101">WdfUsbTargetDeviceSelectConfig</a>
 

 

