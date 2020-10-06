---
UID: NN:portcls.IAdapterPowerManagement3
title: IAdapterPowerManagement3 (portcls.h)
description: The IAdapterPowerManagement3 interface inherits from IUnknown, and it is used for receiving power management messages.
old-location: audio\iadapterpowermanagement3.htm
tech.root: audio
ms.assetid: 5F0729DB-C991-4745-9550-9D25D6836A1F
ms.date: 05/08/2018
keywords: ["IAdapterPowerManagement3 interface"]
ms.keywords: IAdapterPowerManagement3, IAdapterPowerManagement3 interface [Audio Devices], IAdapterPowerManagement3 interface [Audio Devices],described, audio.iadapterpowermanagement3, portcls/IAdapterPowerManagement3
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - IAdapterPowerManagement3
 - portcls/IAdapterPowerManagement3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IAdapterPowerManagement3
---

# IAdapterPowerManagement3 interface


## -description

The IAdapterPowerManagement3 interface inherits from <b>IUnknown</b>, and it is used for receiving power management messages.

To register this interface with PortCls, the adapter driver must call  <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpowermanagement">PcRegisterAdapterPowerManagement</a>.
<div class="alert"><b>Note</b>  If you want to fill the <a href="/previous-versions/ms129154(v=vs.100)">caps structure</a> for your device, your adapter driver can call <b>PcRegisterAdapterPowerManagement</b> from within the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine, or before your driver calls <b>AddDevice.</b></div><div> </div>

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IAdapterPowerManagement3</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IAdapterPowerManagement3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iadapterpowermanagement2">IAdapterPowerManagement2</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpowermanagement">PcRegisterAdapterPowerManagement</a>