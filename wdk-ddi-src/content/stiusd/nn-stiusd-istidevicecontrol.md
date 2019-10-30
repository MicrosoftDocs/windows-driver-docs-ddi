---
UID: NN:stiusd.IStiDeviceControl
title: IStiDeviceControl (stiusd.h)
description: This section describes the methods defined for the IStiDeviceControl COM Interface. Method prototypes are contained in Stiusd.h.
old-location: image\istidevicecontrol_interface_methods.htm
tech.root: image
ms.assetid: de58597a-d10a-45b3-bf75-539e5cd00535
ms.date: 05/03/2018
ms.keywords: IStiDeviceControl, IStiDeviceControl interface [Imaging Devices], IStiDeviceControl interface [Imaging Devices],described, image.istidevicecontrol_interface_methods, stifnc_532906f7-46b9-4874-8099-6be551e77711.xml, stiusd/IStiDeviceControl
ms.topic: interface
f1_keywords:
 - "stiusd/IStiDeviceControl"
req.header: stiusd.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
- stiusd.h
api_name:
- IStiDeviceControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiDeviceControl interface


## -description



This section describes the methods defined for the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/istidevicecontrol-com-interface">IStiDeviceControl COM Interface</a>. Method prototypes are contained in <i>Stiusd.h</i>.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IStiDeviceControl</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IStiDeviceControl</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IStiDeviceControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istidevicecontrol-addref">AddRef</a>
</td>
<td align="left" width="63%">
The <b>IStiDeviceControl::AddRef</b> method increments the reference count for the <b>IStiDeviceControl</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istidevicecontrol-getmydevicehandle">GetMyDeviceHandle</a>
</td>
<td align="left" width="63%">
This topic describes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istidevicecontrol-getmydevicehandle">GetMyDeviceHandle</a> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istidevicecontrol-getmydeviceopenmode">GetMyDeviceOpenMode</a>
</td>
<td align="left" width="63%">
The <b>IStiDeviceControl::GetMyDeviceOpenMode</b> method allows a still image minidriver to obtain the transfer mode that an application specified when it created an instance of a still image device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istidevicecontrol-getmydeviceportname">GetMyDevicePortName</a>
</td>
<td align="left" width="63%">
The <b>IStiDeviceControl::GetMyDevicePortName</b> method allows a user-mode still image minidriver to obtain a device's port name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istidevicecontrol-release">Release</a>
</td>
<td align="left" width="63%">
The <b>IStiDeviceControl::Release</b> method closes the instance of the COM object that was created when a minidriver client called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-initialize">IStiUSD::Initialize</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istidevicecontrol-writetoerrorlog">WriteToErrorLog</a>
</td>
<td align="left" width="63%">
The <b>IStiDeviceControl::WriteToErrorLog</b> method allows a user-mode still image minidriver to write a message into the still image error log.

</td>
</tr>
</table> 

