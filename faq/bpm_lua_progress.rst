Прогресс исполнения долгих процессов в BPM (lua)
==================================================================================================

.. code-block:: lua

	errText2,errNum2= SendWSAsync( GetHTTPListenHostPort(),"/ws/ServeMsgToUser",
		
		JsonToString(
			{
				data = 
				{
				progress = 50,
				title = "Закачивание файлов",

				},
				room = "9999",
				type = "bpms_progress",
				receiver = sys.user_id
			}
			)
	)


	Sleep(2000)


	errText2,errNum2= SendWSAsync( GetHTTPListenHostPort(),"/ws/ServeMsgToUser",
		
		JsonToString(
			{
				data = 
				{
				progress = 90,
				title = "Закачивание текста",

				},
				room = "9999",
				type = "bpms_progress",
				receiver = sys.user_id
			}
			)
	)

	Sleep(2000)