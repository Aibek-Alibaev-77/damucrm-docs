Run Parallel
========================

Процедура вызывает lua скрипт в N потоках . Обеспечивает работу высоконагруженных систем.

..code-block::lua 
    
    0..N-1 - THREAD_CURRENT , --Доступный текущий поток
	THREAD_TOTAL-COUNT - N, --Количество потоков
	THREAD_KEY, --Ключ потока
При запуске дважды с одними параметрами , запуск уже запущенного потока не будет воспроизведен , т.е. в один момент времени может работать  1 ключ/1 поток.
	
 
..code-block::lua

	RunParallel(
	    "qwe" , --Ключ потока
		5, --Количество потоков 
		)

..code-block::lua
    RunParallel(
	    [
            [
		       s = "THREAD_PREFIX:"
		      (THREAD_PREFIX or "")
			  s=s
			  "THREAD KEY:"
			  (THREAD_KEY or "")
			  s=s
			  "THREAD_TOTAL-COUNT:"
			  (THREAD_TOTAL-COUNT or "")
			  s=s
			  "THREAD_CURRENT:"
			  (THREAD_CURRENT or "")
			  s=s
		      print("Parallel test from thread ", s)
            ]
        ]
    )

		
		
  
    
    
    