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
			"token": "asdsadasd.gdg45gdfg.dfgdfg"
		}

II. GET profile:
	Authorization Bearer Token
	
	Response:

		{
			"name": "Sushil",
			"image": "https://asdasdas.com/uploads/dsdsdsds.jpg",
			"leave_balance": 34,
			"encashable": 0
		}

III. GET recent-leaves:
	Authorization Bearer Token

	Response:

		[{
			"no_of_days": 2,
			"from": "2023-03-01",
			"to": "2023-03-02",
			"status": 1
		}]

IV. GET leave-types:
	Authorization Bearer Token

	Response:

		[{
			"leave_type_id": 1,
			"name": "General leaves",
			"balance": 34,
			"can_apply": true,
			"hidden": false
		}, {
			"leave_type_id": 2,
			"name": "Leave without pay",
			"balance": 0,
			"can_apply": false,
			"hidden": false
		}, {
			"leave_type_id": 3,
			"name": "Marriage leave",
			"balance": 10,
			"can_apply": true,
			"hidden": true
		}, {
			"leave_type_id": 4,
			"name": "Bereavement leave",
			"balance": 10,
			"can_apply": true,
			"hidden": true
		}, {
			"leave_type_id": 5,
			"name": "Paternity leave",
			"balance": 10,
			"can_apply": true,
			"hidden": true
		}]

V. POST apply-leave:
	Authorization Bearer Token

	Request:

		{
			"from": "2023-03-10",
			"to": "2023-03-10",
			"leave_type_id": 
		}

	Response:

		{
			"success": true,
			"message": "Leave successfully applied"
		}

VI. 