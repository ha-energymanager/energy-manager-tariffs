# Contribution guidelines
This repository is strictly used to populate Energy Manager with a list of easily imported Electricity Plans from the Australian market.  It is important that the correct format is followed if you wish to contribute.

## Requirements
### Step 1: Export your plan
1) Create your plan in Energy Manager and then select **export**.
2) Copy the contents of the created json file in /config/www/energy-manager/tariffs/export.
### Step 2: Update index.json
1) Add the following block to the index.json file:
```bash
    {
      "label": "{provider} - {plan} - {state} - {dnsp} - {start_date}",
      "file": "{provider}-{plan}-{state}-{dnsp}-{start_date_short}.json",
      "provider": "{provider}",
      "plan": "{plan}",
      "state": "{state}",
      "dnsp": "{dnsp}",
      "effective_from": "{start_date}",
      "source_checked": "{date_now}"
    },
```

Note, follow the format of existing plan details if you are unsure what to add.

### Step 3: Create a new json file specifically for the electricity plan
1) Create a new file named according to the following pattern:  {provider}-{plan}-{state}-{dnsp}-{start_date_short}.json
2) Paste the content from Step 1 above, making sure that it matches exactly the below format: (note, export date will need to be removed, plus some others added. Replace all "x" with the real values.)
```bash
{
  "format": "energy_manager_custom_tariff",
  "version": 1,
  "name": "{provider} - {plan} - {state} - {dnsp} - {start_date}",
  "provider": "{provider}",
  "plan": "{plan}",
  "state": "{state}",
  "dnsp": "{dnsp}",
  "effective_from": "{start_date1",
  "source_checked": "{date_now}",
  "entities": {
    "input_number.other_peak_tariff": x,
    "input_number.other_offpeak_tariff": x,
    "input_number.other_shoulder_tariff": x,
    "input_number.other_additional_tariff": x,
    "input_number.other_export_1_tariff": x,
    "input_number.other_export_2_tariff": x,
    "input_number.other_export_3_tariff": x,
    "input_number.other_export_1_kwh": x,
    "input_number.other_export_2_kwh": x,
    "input_number.other_export_3_kwh": x,
    "input_number.other_export_1_battery_limit": x,
    "input_number.other_export_2_battery_limit": x,
    "input_number.other_export_3_battery_limit": x,
    "input_number.other_free_kwh": x,
    "input_number.electricity_provider_daily_charge": x,
    "input_datetime.other_peak_1_start": "xx:xx:xx",
    "input_datetime.other_peak_1_end": "xx:xx:xx",
    "input_datetime.other_peak_2_start": "xx:xx:xx",
    "input_datetime.other_peak_2_end": "xx:xx:xx",
    "input_datetime.other_peak_3_start": "xx:xx:xx",
    "input_datetime.other_peak_3_end": "xx:xx:xx",
    "input_datetime.other_offpeak_1_start": "xx:xx:xx",
    "input_datetime.other_offpeak_1_end": "xx:xx:xx",
    "input_datetime.other_offpeak_2_start": "xx:xx:xx",
    "input_datetime.other_offpeak_2_end": "xx:xx:xx",
    "input_datetime.other_offpeak_3_start": "xx:xx:xx",
    "input_datetime.other_offpeak_3_end": "xx:xx:xx",
    "input_datetime.other_shoulder_1_start": "xx:xx:xx",
    "input_datetime.other_shoulder_1_end": "xx:xx:xx",
    "input_datetime.other_shoulder_2_start": "xx:xx:xx",
    "input_datetime.other_shoulder_2_end": "xx:xx:xx",
    "input_datetime.other_shoulder_3_start": "xx:xx:xx",
    "input_datetime.other_shoulder_3_end": "xx:xx:xx",
    "input_datetime.other_additional_1_start": "xx:xx:xx",
    "input_datetime.other_additional_1_end": "xx:xx:xx",
    "input_datetime.other_free_1_start": "xx:xx:xx",
    "input_datetime.other_free_1_end": "xx:xx:xx",
    "input_datetime.other_export_1_start": "xx:xx:xx",
    "input_datetime.other_export_1_end": "xx:xx:xx",
    "input_datetime.other_export_2_start": "xx:xx:xx",
    "input_datetime.other_export_2_end": "xx:xx:xx",
    "input_datetime.other_export_3_start": "xx:xx:xx",
    "input_datetime.other_export_3_end": "xx:xx:xx",
    "input_boolean.other_peak_1": x,
    "input_boolean.other_peak_2": x,
    "input_boolean.other_peak_3": x,
    "input_boolean.other_offpeak_1": x,
    "input_boolean.other_offpeak_2": x,
    "input_boolean.other_offpeak_3": x,
    "input_boolean.other_offpeak_bat_1": x,
    "input_boolean.other_offpeak_bat_2": x,
    "input_boolean.other_offpeak_bat_3": x,
    "input_boolean.other_shoulder_1": x,
    "input_boolean.other_shoulder_2": x,
    "input_boolean.other_shoulder_3": x,
    "input_boolean.other_shoulder_bat_1": x,
    "input_boolean.other_shoulder_bat_2": x,
    "input_boolean.other_shoulder_bat_3": x,
    "input_boolean.other_additional_1": x,
    "input_boolean.other_additional_bat_1": x,
    "input_boolean.other_free_1": x,
    "input_boolean.other_free_bat_1": x,
    "input_boolean.other_free_force_import": x,
    "input_boolean.other_free_import_limit": x,
    "input_boolean.other_export_1": x,
    "input_boolean.other_export_2": x,
    "input_boolean.other_export_3": x,
    "input_boolean.other_export_1_export": x,
    "input_boolean.other_export_2_export": x,
    "input_boolean.other_export_3_export": x,
    "input_boolean.other_export_1_limit": x,
    "input_boolean.other_export_2_limit": x,
    "input_boolean.other_export_3_limit": x
  }
}
```
### Step 4: The plan will be reviewed and accepted if the format has been followed correctly.
