**GetStudentUDAreaSetup**
----
	Returns an array of Student UD Setup data in JSON format.
	
* **Version History:**

	TASS v49.3 - Method Added

* **Version:**

	2

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`includelookups [boolean]` - Include lookups                    

   **Optional:**

	`area_code [string]` - Search for eud fields for this area_code

	`eudfld__num [1 - 10] [string]` - Search for eud fields for this eudfld__num come with the area_code

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    "ud_area_setup": [
		{
			"area_desc": "Student Stengths",
			"area_code": 0
		},
		{
			"area_desc": "Transport",
			"area_code": 1
		},
		{
			"area_desc": "Parent Access",
			"area_code": 2
		},
		{
			"area_desc": "Learning Needs",
			"area_code": 3
		},
		{
			"area_desc": "Seasonal Sport",
			"area_code": 4
		},
		{
			"area_desc": "Enrolment Testing",
			"area_code": 5
		},
		{
			"area_desc": "Enterprise Student Ranking",
			"area_code": 500
		}
	]
	```

	```javascript
	"ud_area_field_setup": [
		{
			"eudfld1_desc": "Train pass",
			"area_code": 1,
			"eudfld1_trig": "",
			"eudfld1_sort": 1
		},
		{
			"eudfld2_sort": 1,
			"area_code": 1,
			"eudfld2_trig": "",
			"eudfld2_desc": "Bus pass"
		},
		{
			"eudfld24_desc": "Ferry Pass",
			"eudfld24_sort": 1,
			"eudfld24_trig": "",
			"area_code": 1
		},
		{
			"eudfld25_trig": "",
			"eudfld25_desc": "Approved Passengers",
			"area_code": 1,
			"eudfld25_sort": 1
		},
		{
			"eudfld31_sort": 5,
			"area_code": 1,
			"eudfld31_trig": "Y",
			"eudfld31_desc": "Bus Pass Renewal date"
		},
		{
			"eudfld41_sort": 1,
			"eudfld41_desc": "what is this?",
			"area_code": 1
		}
	],
	"area_code": 1
	```

	```javascript
	"ud_area_ref_data": [
		{
			"eud_desc": "#523",
			"eud_code": "052"
		},
		{
			"eud_desc": "Love",
			"eud_code": 10
		},
		{
			"eud_desc": "#163",
			"eud_code": 163
		},
		{
			"eud_desc": "#486",
			"eud_code": 486
		},
		{
			"eud_desc": "#890",
			"eud_code": 890
		}
	],
	"token": {
		"eudfld_num": 11,
		"includelookups": true,
		"timestamp": "{ts '2019-02-08 14:02:16'}",
		"area_code": 1
	}

    ```
 
* **Error Response:**

    Required `includelookups` not supplied.
	```javascript
	"__invalid": {
		"includelookups": "field is required"
	}
	```
	
	Bool `includelookups` not a valid bool.
	```javascript
	"__invalid": {
		"includelookups": "Value is not a valid boolean."
	}
	```
    
* **Sample Parameters:**

	```javascript
	{"includelookups":"true"}
	```

	```javascript
	{
		"includelookups":"true",
		"area_code":"1"
	}
	```

	```javascript
	{
		"includelookups":"true",
		"area_code":"1",
		"eudfld_num":"11"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://api.tassweb.com.au/tassweb/api/?appcode=DIGIENRO&v=2&method=getStudentUDAreaSetup&token=%2BxYxT3JovxoE2deoaH6feDfyAn%2FcVL0KSCAUjcFpnXM%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="https://api.tassweb.com.au/tassweb/api/">
		<input type="hidden" name="method" value="getStudentUDAreaSetup">
		<input type="hidden" name="appcode" value="DIGIENRO">
		<input type="hidden" name="company" value="10">
		<input type="hidden" name="v" value="2">
		<textarea name="token">+xYxT3JovxoE2deoaH6feDfyAn/cVL0KSCAUjcFpnXM=</textarea>
	</form>
	```
