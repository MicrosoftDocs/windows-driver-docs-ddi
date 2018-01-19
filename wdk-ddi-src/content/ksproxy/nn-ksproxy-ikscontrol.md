---
UID: NN:ksproxy.IKsControl
title: IKsControl
author: windows-driver-content
description: The IKsControl interface provides user-mode methods that control a KS filter or KS pin. See the IKsControl AVStream COM interface for information about the user-mode equivalent of this interface.
old-location: stream\ikscontrol.htm
old-project: stream
ms.assetid: d73cf2fc-15bb-4f45-aae3-fb55bcd072a3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsSynchronousDeviceControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsControl
req.alt-loc: Ksproxy.lib,Ksproxy.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
req.typenames: PIPE_STATE
---

# IKsControl interface



## -description
The <b>IKsControl</b> interface provides user-mode methods that control a KS filter or KS pin. See the <a href="..\ks\nn-ks-ikscontrol.md">IKsControl</a> AVStream COM interface for information about the user-mode equivalent of this interface. 



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsControl</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsControl</b> also has these types of members:

The <b>IKsControl</b> interface has these methods.

Enables or disables an event.

Sends a method to a KS object.

Sets a property or retrieves property information.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsControl</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsControl</b> also has these types of members:

The <b>IKsControl</b> interface has these methods.

Enables or disables an event.

Sends a method to a KS object.

Sets a property or retrieves property information.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsControl</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsControl</b> also has these types of members:

The <b>IKsControl</b> interface has these methods.

Enables or disables an event.

Sends a method to a KS object.

Sets a property or retrieves property information.

 


## -members
The <b>IKsControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KsEvent</a>
</td>
<td align="left" width="63%">
Enables or disables an event.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KsMethod</a>
</td>
<td align="left" width="63%">
Sends a method to a KS object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KsProperty</a>
</td>
<td align="left" width="63%">
Sets a property or retrieves property information.

</td>
</tr>
</table>Enables or disables an event.

Sends a method to a KS object.

Sets a property or retrieves property information.

 


## -remarks
The IID for this interface is IID_IKsControl.


## -see-also
<dl>
<dt>
<a href="..\ks\nn-ks-ikscontrol.md">IKsControl (AVStream COM Interface)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl interface%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

