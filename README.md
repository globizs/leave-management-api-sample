I. OTP based Login API:
	1. POST auth/send-otp

	Request:

		{
			"username": "sushil@globizs.com"
		}

	2. POST auth/verify-otp

	Request:

		{
			"username": "sushil@globizs.com",
			"otp": "123456"
		}

	Response:

		{
			"status": true,
			"message": "some message",
			"data": {
				"token": "asdsadasd.gdg45gdfg.dfgdfg"
			}
		}

II. GET profile:
	Authorization Bearer Token
	
	Response:

		{
			"status": true,
			"message": "some message",
			"data": {
				"name": "Sushil",
				"image": "https://asdasdas.com/uploads/dsdsdsds.jpg",
				"leave_balance": 34,
				"encashable": 0
			}
		}

III. My recent leaves:
	GET recent-leaves
	Authorization Bearer Token

	Response:

		{
			"status": true,
			"message": "some message",
			"data": [{
				"id": 120,
				"label": "Full day",
				"no_of_days": 2,
				"from": "2023-03-01",
				"to": "2023-03-02",
				"status": "Approved",
				"color": "blue"
			}, {
				"id": 130,
				"label": "Full day",
				"no_of_days": 2,
				"from": "2023-03-01",
				"to": "2023-03-02",
				"status": "Rejected",
				"color": "red"
			}]
		}

IV. GET leave-types:
	Authorization Bearer Token

	Response:

		{
			"status": true,
			"message": "some message",
			"data": [{
				"leave_type_id": 1,
				"name": "General leaves",
				"balance": 34,
				"can_apply": true,
				"hidden": false,
				"icon": "https://globizs.com/uploads/icons/general.png"
			}, {
				"leave_type_id": 2,
				"name": "Leave without pay",
				"balance": 0,
				"can_apply": false,
				"hidden": false,
				"icon": "https://globizs.com/uploads/icons/lwp.png"
			}, {
				"leave_type_id": 3,
				"name": "Marriage leave",
				"balance": 10,
				"can_apply": true,
				"hidden": true,
				"icon": "https://globizs.com/uploads/icons/marriage.png"
			}, {
				"leave_type_id": 4,
				"name": "Bereavement leave",
				"balance": 10,
				"can_apply": true,
				"hidden": true,
				"icon": "https://globizs.com/uploads/icons/bereavement.png"
			}, {
				"leave_type_id": 5,
				"name": "Paternity leave",
				"balance": 10,
				"can_apply": true,
				"hidden": true,
				"icon": "https://globizs.com/uploads/icons/paternity.png"
			}]
		}

V. POST apply-leave:
	Authorization Bearer Token

	Request (form-data): (day_section: 1 for morning half, 2 for afternoon)

		"from": "2023-03-10"
		"to": "2023-03-10"
		"half_day": false
		"day_section": NULL
		"leave_type_id": 3
		"reason": "I am sick"

	Response:

		{
			"status": true,
			"message": "Leave successfully applied"
		}

VI. Fetch my leaves
	GET leaves?_page=1
	Authorization Bearer Token

	Response:

		{
			"status": true,
			"message": "some message",
			"data": [{
				"id": 210,
				"label": "Full day",
				"no_of_days": 2,
				"from": "2023-03-01",
				"to": "2023-03-02",
				"status": "Pending",
				"color": "yellow"
			}, {
				"id": 190,
				"label": "Full day",
				"no_of_days": 3,
				"from": "2023-03-01",
				"to": "2023-03-02",
				"status": "Approved",
				"color": "green"
			}]
		}

VI. Fetch all leaves
	GET leaves/all?_page=1
	Authorization Bearer Token

	Response:

		{
			"status": true,
			"message": "some message",
			"data": [{
				"day": "Today",
				"items": [{
					"id": 210,
					"label": "Full day",
					"image": "https://globizs.com/uploads/1.jpg",
					"no_of_days": 2,
					"leave_type": "Sick leave",
					"from": "2023-03-01",
					"to": "2023-03-02",
					"status": "Approved",
					"color": "green",
					"action_text": "Approved/Rejected by HR",
					"show_alert": true
				}, {
					"id": 190,
					"label": "Half day",
					"image": "https://globizs.com/uploads/1.jpg",
					"no_of_days": 3,
					"from": "2023-03-01",
					"to": "2023-03-02",
					"status": "Pending",
					"action_text": null,
					"show_alert": false
				}]
			}, {
				"day": "Tomorrow",
				"items": [{
					"id": 214,
					"label": "Full day",
					"image": "https://globizs.com/uploads/1.jpg",
					"no_of_days": 2,
					"leave_type": "Sick leave",
					"from": "2023-03-01",
					"to": "2023-03-02",
					"status": "Approved",
					"action_text": null,
					"show_alert": true
				}, {
					"id": 220,
					"label": "Half day",
					"image": "https://globizs.com/uploads/1.jpg",
					"no_of_days": 3,
					"from": "2023-03-01",
					"to": "2023-03-02",
					"status": "Pending",
					"action_text": null,
					"show_alert": false
				}]
			}, {
				"day": "28 March",
				"items": [{
					"id": 143,
					"label": "Half day",
					"image": "https://globizs.com/uploads/1.jpg",
					"no_of_days": 2,
					"leave_type": "Sick leave",
					"from": "2023-03-01",
					"to": "2023-03-02",
					"status": "Approved",
					"action_text": "Approved/Rejected by HR",
					"show_alert": false
				}, {
					"id": 120,
					"label": "Full day",
					"image": "https://globizs.com/uploads/1.jpg",
					"no_of_days": 3,
					"from": "2023-03-01",
					"to": "2023-03-02",
					"status": "Pending",
					"action_text": null,
					"show_alert": false
				}]
			}, {
				"day": "29 March",
				"items": [{
					"id": 260,
					"label": "Full day",
					"image": "https://globizs.com/uploads/1.jpg",
					"no_of_days": 2,
					"leave_type": "Sick leave",
					"from": "2023-03-01",
					"to": "2023-03-02",
					"status": "Approved",
					"action_text": "Approved/Rejected by HR",
					"show_alert": false
				}]
			}]
		}

VII. View leave details
	GET leaves/210
	Authorization Bearer Token

	Response:

		{
			"status": true,
			"message": "some message",
			"data": {
				"id": 210,
				"label": "Full day",
				"image": "https://globizs.com/uploads/1.jpg",
				"name": "Sushil",
				"no_of_days": 2,
				"leave_type": "General",
				"from": "2023-03-01",
				"to": "2023-03-02",
				"status": "Approved",
				"show_alert": false,
				"leave_balance": 34,
				"reason": "Fever from yesterday",
				"applied_date": "2023-03-01 08:00",
				"can_approve": true,
				"approvals": [{
					"action_text": "Approved/Rejected by HOD",
				}, {
					"action_text": "Approved/Rejected by HR",
				}, {
					"action_text": "Approved/Rejected by Director",
				}]
			}
		}

VIII. Fetch pending leaves assigned to me for approval (HOD/HR/Director)
	GET leaves/pending?_page=1&limit=10
	Authorization Bearer Token

	Response:

		{
			"status": true,
			"message": "some message",
			"data": [{
				"id": 260,
				"label": "Full day",
				"image": "https://globizs.com/uploads/1.jpg",
				"no_of_days": 2,
				"leave_type": "Sick leave",
				"from": "2023-03-01",
				"to": "2023-03-02",
				"status": "Pending",
				"action_text": null,
				"show_alert": true
			}, {
				"id": 280,
				"label": "Full day",
				"image": "https://globizs.com/uploads/1.jpg",
				"no_of_days": 2,
				"leave_type": "Sick leave",
				"from": "2023-03-01",
				"to": "2023-03-02",
				"status": "Pending",
				"action_text": null,
				"show_alert": true
			}]
		}

IX. Approve leave:
	POST leaves/210/approve
	Authorization Bearer Token

	Response:

		{
			"status": 1,
			"remark": null
		}
