---
UID: NN:ksproxy.IKsAggregateControl
title: IKsAggregateControl (ksproxy.h)
description: The IKsAggregateControl interface provides methods that add and remove COM servers as aggregate providers on KS objects that support the interface.
old-location: stream\iksaggregatecontrol.htm
tech.root: stream
ms.assetid: ed239516-bbaf-4e16-a3b8-4f9f34cab4ef
ms.date: 04/23/2018
keywords: ["IKsAggregateControl interface"]
ms.keywords: IKsAggregateControl, IKsAggregateControl interface [Streaming Media Devices], IKsAggregateControl interface [Streaming Media Devices],described, ksproxy/IKsAggregateControl, ksproxy_ccd980b0-abd1-4354-9f2c-3c0613b18d07.xml, stream.iksaggregatecontrol
f1_keywords:
 - "ksproxy/IKsAggregateControl"
 - "IKsAggregateControl"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsAggregateControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsAggregateControl interface

## -description

The **IKsAggregateControl** interface provides methods that add and remove COM servers as aggregate providers on KS objects that support the interface.

The interface identifier (IID) for this interface is IID_IKsAggregateControl.

## -inheritance

The **IKsAggregateControl** interface inherits from the [IUnknown](https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown) interface. **IKsAggregateControl** also has these types of members:

- **Methods**

## -remarks

All property, method, and event sets that a KS filter or pin supports can be represented on the DirectShow proxy representation of the filter or pin object by zero or more aggregated interfaces, dialogs, and so on. These client aggregated interfaces are set extensions that can then be used to communicate to the underlying KS object in order to represent the functionality of the set. A set extension is a registered COM server, which is loaded through **CoCreateInstance** by the KS filter or pin at handle creation time.

The primary purpose of set extensions is to allow aggregation of interfaces so as to support some set through one or more COM interfaces. However, an implementation may also include support of dialogs, asynchronous processing in threads, and so on. Registration of a set handler allows one to indicate either a specific interface that is to be aggregated or that an unnamed list of interfaces will be exposed. In the first case, only appropriate queries are sent to the object, and in the latter all queries that do not match an interface already supported are sent to this extension object.

An extension may also receive notifications of state changes by supporting the **IDistributorNotify** interface. If the extension object supports this interface, it will be notified of all start, stop, and pause state changes before the filter itself processes those changes. In addition, the **IDistributorNotify::NotifyGraphChange** method is used on pin object extensions to indicate that the KS pin instance has just closed. This method is only used for pin interface extensions and is called on an extension object each time the pin is disconnected or reconnected, while the extension object is still loaded and aggregated by the pin object.

Notification on pin-connection changes is required because the extensions are not unloaded when a pin is disconnected. Instead, extensions are loaded the first time the pin is connected and left loaded through disconnects and reconnects, unless a reconnect indicates that the particular extension set is not supported on the pin any longer. This fact allows an extension object to retain state between reconnections, but it also means that an extension might require information about whether the KS pin is currently connected. The extension can determine this information by calling the **IKsObject::KsGetObjectHandle** method to query for the KS pin's object handle when the extension receives a **NotifyGraphChange** call. When the extension is first loaded, it can assume the pin is connected and any subsequent notification may imply a disconnection, or reconnection. Thus, the notification occurs after the actual change occurs, as opposed to state changes, which notify before.

A set extension is basically a COM server that optionally exposes the **IDistributorNotify** interface and zero or more other aggregated interfaces that can be used by a client of the filter to manipulate sets that the extension object represents. On an extension object creation request through **CoCreateInstance**, the server is always presented an outer **IUnknown** with which to create the COM object. This **IUnknown** is an interface on the filter or pin object that is loading set extensions. The **IUnknown** interface pointer may be used to query information or interfaces from the filter or pin, such as **IKsControl**. However, no reference should be left on the outer object, as it will result in a circular reference count. Using the interfaces without a reference count is acceptable, because the extension is aggregated by the outer object and, by definition, is destroyed when the outer object's reference count reaches zero.

In order to load set extensions, the proxy looks up the GUID of each set collected from the filter or pin, determining if each is present in the registry. The GUID for each set that is to have an extension loaded is:

```cpp
HKLM\System\CurrentControlSet\Control\MediaInterfaces\{set guid}
```

If this subkey is present, the GUID of the set corresponds directly to the GUID used in the COM server parameter of the **CoCreateInstance** call. Each subkey may also have a named binary value iid that contains the binary representation of the GUID for the interface to be aggregated for this set extension. This is the interface GUID that will cause a **QueryInterface** on the filter or pin to be sent to the COM server for this extension. If this named value is not present under the subkey, all unknown **QueryInterface** calls will be routed through this extension object, thus allowing it to support many interfaces for a particular set exposed on the underlying object. The GUID of the set could be used as the interface identifier by either setting iid to be the GUID of the set, or by not setting an iid value. In the latter case, additional queries not supported may be sent to the extension object.

Although the **MediaInterfaces** registry key may be used to explicitly indicate which interface (if any) the provider aggregates, the entire entry need not be present. The implication being that any COM server can be loaded through **IKsAggregateControl** so that this COM server provides aggregated interfaces, whether the COM server is listed under the **MediaInterfaces** registry key.

For sets that are supported and already have defined extension object handlers that are automatically registered at installation time or when a specific type of device is added to the system, the driver installation need not perform any additional work in exposing these COM interfaces for their filter. However, to expose COM interfaces for private sets, both the **MediaInterfaces** entry and the COM server entry need to be added when the filter is installed.

The proxy also allows a filter to override the COM server for a set registered under **MediaInterfaces**. To override, create a **SetAliases** key under the Plug and Play interface registry key. **CLSID** and **FriendlyName** are located in the path **HKLM\\...\SetAliases**.

Also, enter the named value {*set guid*}, which is the string format of the set GUID, as the binary value of the GUID for the replacement **MediaInterfaces** subkey. Thus, for this filter or any object under this filter, all sets with this GUID will use this alternate GUID to look for a **MediaInterfaces** entry rather than the GUID of the set itself. The new **MediaInterfaces** entry would be registered as usual.

For more information about **IDistributorNotify**, **IUnknown**, and **CoCreateInstance**, see the Microsoft Windows SDK documentation.

## -see-also

[IKsControl](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol)

[IKsObject::KsGetObjectHandle](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksobject-ksgetobjecthandle)

[KsAddAggregate](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksaggregatecontrol-ksaddaggregate)

[KsRemoveAggregate](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksaggregatecontrol-ksremoveaggregate)
