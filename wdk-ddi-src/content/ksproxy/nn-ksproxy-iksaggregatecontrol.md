---
UID: NN:ksproxy.IKsAggregateControl
title: IKsAggregateControl
author: windows-driver-content
description: The IKsAggregateControl interface provides methods that add and remove COM servers as aggregate providers on KS objects that support the interface.
old-location: stream\iksaggregatecontrol.htm
old-project: stream
ms.assetid: ed239516-bbaf-4e16-a3b8-4f9f34cab4ef
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IKsAggregateControl, IKsAggregateControl interface [Streaming Media Devices], IKsAggregateControl interface [Streaming Media Devices],described, ksproxy/IKsAggregateControl, ksproxy_ccd980b0-abd1-4354-9f2c-3c0613b18d07.xml, stream.iksaggregatecontrol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ksproxy.h
req.include-header: 
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsAggregateControl
product: Windows
targetos: Windows
req.typenames: 
---

# IKsAggregateControl interface


## -description


The <b>IKsAggregateControl</b> interface provides methods that add and remove COM servers as aggregate providers on KS objects that support the interface. 

The interface identifier (IID) for this interface is IID_IKsAggregateControl.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsAggregateControl</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsAggregateControl</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsAggregateControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/9808bdb9-17f9-4a80-90c7-e85ab35b74ae">KsAddAggregate</a>
</td>
<td align="left" width="63%">
Adds a COM server as an aggregate provider to a KS filter or pin.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/f625b1ed-ccab-4072-9eb9-c4ebbddb1199">KsRemoveAggregate</a>
</td>
<td align="left" width="63%">
Removes a previously added COM server aggregate provider from a KS filter or pin.

</td>
</tr>
</table> 


## -remarks



<h3><a id="ddk_iksaggregatecontrol_ks"></a><a id="DDK_IKSAGGREGATECONTROL_KS"></a></h3>
All property, method, and event sets that a KS filter or pin supports can be represented on the DirectShow proxy representation of the filter or pin object by zero or more aggregated interfaces, dialogs, and so on. These client aggregated interfaces are set extensions that can then be used to communicate to the underlying KS object in order to represent the functionality of the set. A set extension is a registered COM server, which is loaded through <b>CoCreateInstance</b> by the KS filter or pin at handle creation time.

The primary purpose of set extensions is to allow aggregation of interfaces so as to support some set through one or more COM interfaces. However, an implementation may also include support of dialogs, asynchronous processing in threads, and so on. Registration of a set handler allows one to indicate either a specific interface that is to be aggregated or that an unnamed list of interfaces will be exposed. In the first case, only appropriate queries are sent to the object, and in the latter all queries that do not match an interface already supported are sent to this extension object.

An extension may also receive notifications of state changes by supporting the <b>IDistributorNotify</b> interface. If the extension object supports this interface, it will be notified of all start, stop, and pause state changes before the filter itself processes those changes. In addition, the <b>IDistributorNotify::NotifyGraphChange</b> method is used on pin object extensions to indicate that the KS pin instance has just closed. This method is only used for pin interface extensions and is called on an extension object each time the pin is disconnected or reconnected, while the extension object is still loaded and aggregated by the pin object.

Notification on pin-connection changes is required because the extensions are not unloaded when a pin is disconnected. Instead, extensions are loaded the first time the pin is connected and left loaded through disconnects and reconnects, unless a reconnect indicates that the particular extension set is not supported on the pin any longer. This fact allows an extension object to retain state between reconnections, but it also means that an extension might require information about whether the KS pin is currently connected. The extension can determine this information by calling the <b>IKsObject::KsGetObjectHandle</b> method to query for the KS pin's object handle when the extension receives a <b>NotifyGraphChange</b> call. When the extension is first loaded, it can assume the pin is connected and any subsequent notification may imply a disconnection, or reconnection. Thus, the notification occurs after the actual change occurs, as opposed to state changes, which notify before.

A set extension is basically a COM server that optionally exposes the <b>IDistributorNotify</b> interface and zero or more other aggregated interfaces that can be used by a client of the filter to manipulate sets that the extension object represents. On an extension object creation request through <b>CoCreateInstance</b>, the server is always presented an outer <b>IUnknown</b> with which to create the COM object. This <b>IUnknown</b> is an interface on the filter or pin object that is loading set extensions. The <b>IUnknown</b> interface pointer may be used to query information or interfaces from the filter or pin, such as <b>IKsControl</b>. However, no reference should be left on the outer object, as it will result in a circular reference count. Using the interfaces without a reference count is acceptable, because the extension is aggregated by the outer object and, by definition, is destroyed when the outer object's reference count reaches zero.

In order to load set extensions, the proxy looks up the GUID of each set collected from the filter or pin, determining if each is present in the registry. The GUID for each set that is to have an extension loaded is:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HKLM\System\CurrentControlSet\Control\MediaInterfaces\{set guid}</pre>
</td>
</tr>
</table></span></div>
If this subkey is present, the GUID of the set corresponds directly to the GUID used in the COM server parameter of the <b>CoCreateInstance</b> call. Each subkey may also have a named binary value iid that contains the binary representation of the GUID for the interface to be aggregated for this set extension. This is the interface GUID that will cause a <b>QueryInterface</b> on the filter or pin to be sent to the COM server for this extension. If this named value is not present under the subkey, all unknown <b>QueryInterface</b> calls will be routed through this extension object, thus allowing it to support many interfaces for a particular set exposed on the underlying object. The GUID of the set could be used as the interface identifier by either setting iid to be the GUID of the set, or by not setting an iid value. In the latter case, additional queries not supported may be sent to the extension object.

Although the <b>MediaInterfaces</b> registry key may be used to explicitly indicate which interface (if any) the provider aggregates, the entire entry need not be present. The implication being that any COM server can be loaded through <b>IKsAggregateControl</b> so that this COM server provides aggregated interfaces, whether the COM server is listed under the <b>MediaInterfaces</b> registry key.

For sets that are supported and already have defined extension object handlers that are automatically registered at installation time or when a specific type of device is added to the system, the driver installation need not perform any additional work in exposing these COM interfaces for their filter. However, to expose COM interfaces for private sets, both the <b>MediaInterfaces</b> entry and the COM server entry need to be added when the filter is installed.

The proxy also allows a filter to override the COM server for a set registered under <b>MediaInterfaces</b>. To override, create a <b>SetAliases</b> key under the Plug and Play interface registry key. <b>CLSID</b> and <b>FriendlyName</b> are located in the path <b>HKLM\...\SetAliases</b>.

Also, enter the named value {<i>set guid</i>}, which is the string format of the set GUID, as the binary value of the GUID for the replacement <b>MediaInterfaces</b> subkey. Thus, for this filter or any object under this filter, all sets with this GUID will use this alternate GUID to look for a <b>MediaInterfaces</b> entry rather than the GUID of the set itself. The new <b>MediaInterfaces</b> entry would be registered as usual.

For more information about <b>IDistributorNotify</b>, <b>IUnknown</b>, and <b>CoCreateInstance</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559766">IKsControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559890">IKsObject::KsGetObjectHandle</a>



<a href="https://msdn.microsoft.com/9808bdb9-17f9-4a80-90c7-e85ab35b74ae">KsAddAggregate</a>



<a href="https://msdn.microsoft.com/f625b1ed-ccab-4072-9eb9-c4ebbddb1199">KsRemoveAggregate</a>
 

 

