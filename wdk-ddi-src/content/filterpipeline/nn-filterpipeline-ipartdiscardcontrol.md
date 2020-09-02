---
UID: NN:filterpipeline.IPartDiscardControl
title: IPartDiscardControl (filterpipeline.h)
description: The filter pipeline supports the discard control.
old-location: print\ipartdiscardcontrol.htm
tech.root: print
ms.assetid: 30c6fb0c-42ea-441f-b0a2-3310f8a5b407
ms.date: 04/20/2018
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

The filter pipeline supports the discard control. Filters can use this object, if they obtain it from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-ixpsdocumentprovider-getxpspart">IXpsDocumentProvider::GetXpsPart</a> method. In some cases, processing this object might just include forwarding it to the next filter by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-ixpsdocumentconsumer-sendxpsunknown">IXpsDocumentConsumer::SendXpsUnknown</a> method.

Filters can also create discard controls. To create a discard control, the filter must create an object that implements the <b>IPartDiscardControl</b> interface. Because the filter transfers ownership of the discard control when it sends it to the next filter, the filter must manage the lifetime of the discard control. If a filter creates a discard control, the filter DLL must not unload until the discard control has been released.

## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPartDiscardControl</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPartDiscardControl</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

