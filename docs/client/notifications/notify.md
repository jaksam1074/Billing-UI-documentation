# Replace default notifications

Triggered after notifying player client side

## Event
``` lua
AddEventHandler("billing_ui:notify", function(message)

end)
```

### Parameters

| Name              | Data Type | Description                 |
| -                 | -         | -                             |
| `message`         | string    | Message of the notification  |

## Example (you can place it in the folder integrations/cl_integrations.lua of the script)
``` lua
RegisterNetEvent("billing_ui:framework:ready", function() 
    -- Disables the default script notification (otherwise there would be 2 notifications)
    exports["billing_ui"]:disableScriptEvent("billing_ui:notify")
end)

RegisterNetEvent("billing_ui:notify", function(message)
    TriggerEvent("external_script:notify", message)
end)
```