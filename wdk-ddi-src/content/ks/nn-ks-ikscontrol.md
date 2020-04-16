---
UID: NN:ks.IKsControl
title: IKsControl (ks.h)
description: The IKsControl interface is a COM-style interface implemented on AVStream filters and pins.
old-location: stream\ikscontrol8.htm
tech.root: stream
ms.assetid: 33eb0244-e0f3-4db7-b6df-2668e826fbd8
ms.date: 04/23/2018
keywords: ["IKsControl interface"]
ms.keywords: IKsControl, IKsControl interface [Streaming Media Devices], IKsControl interface [Streaming Media Devices],described, avintfc_fc0ad706-c416-40f7-b213-5467fcebeb72.xml, ks/IKsControl, stream.ikscontrol8
f1_keywords:
 - "ks/IKsControl"
req.header: ks.h
req.include-header: Ks.h
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
- Ks.h
api_name:
- IKsControl
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: 19H1
---

# IKsControl interface

## -description

The **IKsControl** interface is a COM-style interface implemented on AVStream filters and pins. It enables clients in kernel mode to access AVStream automation objects (properties, methods, and events).

See the [IKsControl (ksproxy.h)](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol) kernel-streaming proxy COM interface for information about the kernel-mode equivalent of this interface.

## -inheritance

The **IKsControl** interface inherits from the [IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

Minidrivers typically acquire the **IKsControl** interface through a call to [KsPinGetConnectedFilterInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedfilterinterface) or [KsPinGetConnectedPinInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedpininterface). Because this is a COM-style interface, the function call to obtain this interface calls the **QueryInterface** method, which in turn calls the **AddRef** method. Therefore, the minidriver does not have to perform these steps.

However, as soon as the client is finished with the **IKsControl** interface, it must release **IKsControl** with a call to the **Release** method.

Minidrivers that are written in C manipulate the **IKsControl** interface as a structure that contains a pointer to a table of functions instead of a C++ abstract base class.

A client that is written in C++ does the following:

```cpp
IKsControl *Control;

if (NT_SUCCESS (
  KsPinGetConnectedPinInterface (
    Pin,
    IID_IKsControl,
    (PVOID *)&Control) )
) {
  Control -> KsProperty (...);
  Control -> Release ();
}
```

However, a client that is written in C uses this code instead:

```cpp
IKsControl *Control;

    If (NT_SUCCESS (
      KsPinGetConnectedPinInterface (
        Pin,
        IID_IKsControl,
        (PVOID *)&Control) )
    ) {
      Control -> lpVtbl -> KsProperty (...);
      Control -> lpVtbl -> Release ();
    }
```

For more information, see [AVStream Overview](https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-overview).

## -see-also

[IKsControl(ksproxy.h)](https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol)

[KsPinGetConnectedFilterInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedfilterinterface)

[KsPinGetConnectedPinInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedpininterface)
