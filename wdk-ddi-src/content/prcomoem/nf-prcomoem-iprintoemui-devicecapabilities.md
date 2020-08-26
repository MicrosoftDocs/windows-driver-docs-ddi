---
UID: NF:prcomoem.IPrintOemUI.DeviceCapabilities
title: IPrintOemUI::DeviceCapabilities (prcomoem.h)
description: The IPrintOemUI::DeviceCapabilities method enables a user interface plug-in to specify customized device capabilities.
old-location: print\iprintoemui_devicecapabilities.htm
tech.root: print
ms.assetid: a3d3e986-41ab-489a-a930-b10e9989553f
ms.date: 04/20/2018
keywords: ["IPrintOemUI::DeviceCapabilities"]
ms.keywords: DeviceCapabilities, DeviceCapabilities method [Print Devices], DeviceCapabilities method [Print Devices],IPrintOemUI interface, IPrintOemUI interface [Print Devices],DeviceCapabilities method, IPrintOemUI.DeviceCapabilities, IPrintOemUI::DeviceCapabilities, prcomoem/IPrintOemUI::DeviceCapabilities, print.iprintoemui_devicecapabilities, print_unidrv-pscript_ui_c484fb57-6990-4a0c-848d-5992051cb71d.xml
f1_keywords:
 - "prcomoem/IPrintOemUI.DeviceCapabilities"
 - "IPrintOemUI.DeviceCapabilities"
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemUI.DeviceCapabilities
targetos: Windows
req.typenames: 
---

# IPrintOemUI::DeviceCapabilities


## -description


The <code>IPrintOemUI::DeviceCapabilities</code> method enables a user interface plug-in to specify customized device capabilities.


## -parameters




### -param poemuiobj

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure.


### -param hPrinter

Caller-supplied handle to the printer device.


### -param pDeviceName

Caller-supplied pointer to a string representing the device name.


### -param wCapability

Caller-supplied flag indicating the type of information the method should return. For a list of flags, see the description of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicecapabilities">DrvDeviceCapabilities</a> function.


### -param pOutput

Caller-supplied pointer to a buffer to receive the requested information. The type of information returned is dependent on the flag specified by <i>wCapability</i>.


### -param pPublicDM

Caller-supplied pointer to a validated <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure.


### -param pOEMDM

Caller-supplied pointer to the user interface plug-in's private DEVMODEW structure members.


### -param dwOld

Caller-supplied return value from the printer driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicecapabilities">DrvDeviceCapabilities</a> function, or from another user interface plug-in. For more information, see the following Remarks section.


### -param dwResult

A return value that is dependent on the flag specified by <i>wCapability</i>. For more information, see the description of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicecapabilities">DrvDeviceCapabilities</a> function and the following Remarks section.


## -returns



The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_DEVCAP_OUTPUT_FULL_REPLACEMENT</b></dt>
</dl>
</td>
<td width="60%">
The plug-in intends to use the buffer that is pointed to by the <i>pOutput</i> parameter for its own purposes. This return value is defined in prcomoem.h. For more information about when to use this return value, see the following Remarks section.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



A user interface plug-in's <code>IPrintOemUI::DeviceCapabilities</code> method performs the same types of operations as the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicecapabilities">DrvDeviceCapabilities</a> function that is exported by user-mode printer interface DLLs. The method specifies capabilities provided by the printer.

You can use the <code>IPrintOemUI::DeviceCapabilities</code> method to preempt Unidrv support for a capability, or to add a capability that the printer driver doesn't provide. The driver calls <code>IPrintOemUI::DeviceCapabilities</code> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicecapabilities">DrvDeviceCapabilities</a> function.

If the <code>IPrintOemUI::DeviceCapabilities</code> method indicates customized support for a capability (by setting appropriate bits in response to a received DC_FIELDS flag), customized code must completely support the capability. Complete support typically includes returning information about the capability in response to calls to the <code>IPrintOemUI::DeviceCapabilities</code> method, plus providing appropriate user-mode or kernel-mode code to implement the capability.

If <code>IPrintOemUI::DeviceCapabilities</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation. Each time a plug-in's <code>IPrintOemUI::DeviceCapabilities</code> method is called, its <i>dwOld</i> input value is the return value from the previously called plug-in's <code>IPrintOemUI::DeviceCapabilities</code> method. For the first plug-in called, <i>dwOld</i> contains the return value from the printer driver's <b>DrvDeviceCapabilities</b> function. Likewise, the buffer pointed to by <i>pOutput</i> contains, on input, any contents placed there by a previously called <code>IPrintOemUI::DeviceCapabilities</code> method or <b>DrvDeviceCapabilities</b> function.

For multiple user interface plug-ins to work in conjunction with each other, each <code>IPrintOemUI::DeviceCapabilities</code> method must obey the following rules:

<ul>
<li>
If a user interface plug-in does not support a specified capability, its <code>IPrintOemUI::DeviceCapabilities</code> method should just return the contents of the <i>dwOld</i> parameter in <i>dwResult</i>.

</li>
<li>
If a user interface plug-in supports the capability, its <code>IPrintOemUI::DeviceCapabilities</code> method should ignore <i>dwOld</i> and the contents of the buffer pointed to by <i>pOutput</i>. It should provide a return value and buffer contents appropriate for indicating that it supports the specified capability. If the method detects an error, it should return GDI_ERROR in <i>dwResult</i>.

</li>
<li>
If you want a user interface plug-in to modify the capabilities information received in the buffer pointed to by <i>pOutput</i>, its <code>IPrintOemUI::DeviceCapabilities</code> method should modify the buffer contents and return an appropriate return value in <i>dwResult</i>. For example, if <i>wCapability</i> is DC_FIELDS, the method should OR the bits it needs to set with the bits that are set in <i>dwOld</i>, and return the result of the OR operation in <i>dwResult</i>.

</li>
<li>
The preceding rules should be followed even if the received contents of <i>dwOld</i> is GDI_ERROR.

</li>
</ul>
When the driver's <b>DrvDeviceCapabilities</b> function is called with the DC_FIELDS flag set, the function calls all <code>IPrintOemUI::DeviceCapabilities</code> methods, also specifying DC_FIELDS, and returns the union of all set bits to the caller.

The S_DEVCAP_OUTPUT_FULL_REPLACEMENT return value is new in Windows Vista, and applies to both Unidrv and Pscript5 user interface plug-ins. A plug-in should use the S_DEVCAP_OUTPUT_FULL_REPLACEMENT return value only if it requires complete control over what is placed in the buffer that is pointed to by the <i>pOutput</i> parameter. Neither the Unidrv nor the Pscript5 core driver will place data in the <i>pOutput</i> buffer when the plug-in returns S_DEVCAP_OUTPUT_FULL_REPLACEMENT. A plug-in might need to return this value when a setting in the <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure (which is pointed to by the <i>pPublicDM</i> and <i>pOEMDM</i> parameters) indicates to the user interface plug-in that it should report device capability data that is different from that specified in the GPD or PPD file. For example, a DEVMODEW structure that specifies photo printing might require a different set of paper types than those that are specified in the GPD or PPD file. In such a situation, and regardless of the values of the <i>pOutput</i> and <i>dwOld</i> parameters, the plug-in should return S_DEVCAP_OUTPUT_FULL_REPLACEMENT, and should set the <i>dwResult</i> parameter to the number of paper types that it intends to report. If <i>pOutput</i> is not <b>NULL</b>, the plug-in should also fill the buffer that is pointed to by <i>pOutput</i> with the desired set of paper types, and should set <i>dwResult</i> to the number of paper types that the plug-in intends to report. 

When multiple user interface plug-ins are active at the same time, and one of them returns S_DEVCAP_OUTPUT_FULL_REPLACEMENT, the Unidrv or Pscript5 core driver interprets this return value to mean that the plug-ins intend to provide full replacement output data. As a result, the core driver does not place any data into the <i>pOutput</i> buffer before it calls the plug-ins. (The core driver calls the plug-ins in the same order that was specified for their installation.)

In situations where the values that the core driver places in the <i>pOutput</i> buffer do not need to be replaced, the plug-in should return S_OK. The Unidrv and Pscript5 core drivers recognize the S_DEVCAP_OUTPUT_FULL_REPLACEMENT return value only for device capabilities that use the <i>pOutput</i> buffer--in other words, when the <i>wCapability</i> parameter is set to one of the following flags:

DC_PAPERNAMES

DC_PAPERS

DC_PAPERSIZE

DC_BINNAMES

DC_BINS

DC_NUP

DC_PERSONALITY

DC_MEDIAREADY

DC_MEDIATYPENAMES

DC_MEDIATYPES

DC_ENUMRESOLUTIONS

For more information about creating and installing user interface plug-ins, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicecapabilities">DrvDeviceCapabilities</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemui">IPrintOemUI</a>
 

 

