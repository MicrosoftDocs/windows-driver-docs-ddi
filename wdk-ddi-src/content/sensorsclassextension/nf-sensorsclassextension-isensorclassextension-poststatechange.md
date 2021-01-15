---
UID: NF:sensorsclassextension.ISensorClassExtension.PostStateChange
title: ISensorClassExtension::PostStateChange (sensorsclassextension.h)
description: The ISensorClassExtension::PostStateChange method notifies the sensor class extension about a change in the operational state of the sensor.
old-location: sensors\isensorclassextension_poststatechange.htm
tech.root: sensors
ms.date: 05/03/2018
keywords: ["ISensorClassExtension::PostStateChange"]
ms.keywords: ISensorClassExtension interface [Sensor Devices],PostStateChange method, ISensorClassExtension.PostStateChange, ISensorClassExtension::PostStateChange, PostStateChange, PostStateChange method [Sensor Devices], PostStateChange method [Sensor Devices],ISensorClassExtension interface, Sensor_IFaces_b6cc2565-ed4f-48cb-83ea-8d03322c2670.xml, sensors.isensorclassextension_poststatechange, sensorsclassextension/ISensorClassExtension::PostStateChange
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 7,Available in Windows 7.
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ISensorClassExtension::PostStateChange
 - sensorsclassextension/ISensorClassExtension::PostStateChange
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - SensorsClassExtension.lib
 - SensorsClassExtension.dll
api_name:
 - ISensorClassExtension::PostStateChange
---

# ISensorClassExtension::PostStateChange


## -description

The <b>ISensorClassExtension::PostStateChange</b> method notifies the sensor class extension about a change in the operational state of the sensor.

## -parameters

### -param pwszSensorID 

[in]
<b>LPWSTR</b> that contains the ID for the sensor for which the driver is raising the event.

### -param state

#### - State [in]


<a href="/windows-hardware/drivers/ddi/sensorsclassextension/ne-sensorsclassextension-__midl___midl_itf_windowssensorclassextension_0000_0000_0001">SensorState</a> value that indicates the new state.

## -returns

This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.

|Return code|Description|
|--- |--- |
|S_OK|The method succeeded.|
|E_POINTER|A required pointer argument was NULL.|
|HRESULT_FROM_WIN32(ERROR_CAN_NOT_COMPLETE)|The class extension is not initialized.|

## -remarks

Sensor state information is also available through the <a href="/windows-hardware/drivers/sensors/sensor-properties2">SENSOR_PROPERTY_STATE</a> property key.

<div class="code"></div>

#### Examples

The following example code demonstrates a function that posts a state-changed event.

```cpp
HRESULT PostStateEvent()
{
    // Validate that we have a pointer to the class extension.
    HRESULT hr = (NULL == m_spSensorCXT) ? E_UNEXPECTED : S_OK ;

    if (SUCCEEDED(hr))
    {
        SensorState st;

        // Retrieve the sensor state
        hr = m_pDdi->GetSensorState(&st);

        if (SUCCEEDED(hr))
        {
            // Post the state change event.
            hr = m_spSensorCXT->PostStateChange(g_wszSensorID, st);
        }
    }

    return hr;
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensorclassextension">ISensorClassExtension</a>



<a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientsubscribetoevents">ISensorDriver::OnClientSubscribeToEvents</a>



<a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-onclientunsubscribefromevents">ISensorDriver::OnClientUnsubscribeFromEvents</a>

