---
UID: NN:filterpipeline.IPartDiscardControl
title: IPartDiscardControl (filterpipeline.h)
description: The filter pipeline supports the discard control.
tech.root: print
ms.date: 06/10/2021
keywords: ["IPartDiscardControl interface"]
ms.keywords: IPartDiscardControl, IPartDiscardControl interface [Print Devices], IPartDiscardControl interface [Print Devices],described, filterpipeline/IPartDiscardControl, filterpipeline_c29b91d3-ecf6-4697-bf5f-5b536cfb7071.xml, print.ipartdiscardcontrol
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPartDiscardControl
 - filterpipeline/IPartDiscardControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPartDiscardControl
---

# IPartDiscardControl interface

## -description

The filter pipeline supports the discard control. Filters can use this object, if they obtain it from [IXpsDocumentProvider::GetXpsPart](./nf-filterpipeline-ixpsdocumentprovider-getxpspart.md) method. In some cases, processing this object might just include forwarding it to the next filter by using the [IXpsDocumentConsumer::SendXpsUnknown](./nf-filterpipeline-ixpsdocumentconsumer-sendxpsunknown.md) method.

Filters can also create discard controls. To create a discard control, the filter must create an object that implements the **IPartDiscardControl** interface. Because the filter transfers ownership of the discard control when it sends it to the next filter, the filter must manage the lifetime of the discard control. If a filter creates a discard control, the filter DLL must not unload until the discard control has been released.

## -inheritance

The **IPartDiscardControl** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.