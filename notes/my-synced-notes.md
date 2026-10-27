
 


# LangChain, LLM’s, Prompt Engineering


Open VS code with a new workspace folder and then open terminal in it. 
We will first install UV in through the terminal, with the command for windows as - 


**Command for UV installation in windows :**


powershell -ExecutionPolicy ByPass -c "irm [https://astral.sh/uv/install.ps1](https://astral.sh/uv/install.ps1) | iex"


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/e4c3cec8-5843-4603-a630-258d940905b2/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=d818937b8d139bf65ea67eea660610f04aebdbaa54b64d8619e46b17a0b54d84&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Then comes the step of creating an environment and activating it, the command for creating an environment or a virtual machine is - 


**Command for checking the UV version and creating a virtual environment :**


uv  - -version  (remove the space between the dashes in the terminal) 


uv venv  (for creating a virtual machine)


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/829e0b51-f98c-4c60-b2db-7321059aca9c/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=78e95ef730b5896a7f79f5c0bb36e63c47146b84992ace1c882e1667313e15e5&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Then you have to activate the virtual machine using the same command you can see above in the “Activate with: .venv\scripts\activate”. The command you have to put in the terminal would be whatever written in your terminal after the “Activate with: “ statement, as in my case the command would be : 


**Command for activating the virtual machine :** 


.venv\scripts\activate


Once the activation of the virtual machine is done, the next step includes setting up the VM or the project and adding langchain into the system - 


**Command to set up the project/VM :** 


uv init  (this will create a .toml file in your sytem)


**Command for adding langchain -** 


uv add langchain


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/17ea5185-3b80-4d08-9a3a-32e50948284d/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=8336eaa3e5d9671ef937dff59094e16268f8a263147f43d0ec702b44fd759ce2&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


now to check whether langchain has been installed in our sytem or not, make a new [test.py](http://test.py/) file and run the following code prompt


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/ee721c0f-f2f9-43bd-b851-714c018c4c75/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=f52f09ce4100e45a22d9172b4dcd115f8773192199bbfd282548f262e1e1c2d1&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


which will produce an output as such -


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/6f17f668-2e1e-4375-958f-1add5cad43c9/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=545662303f9a815d7061879f89c3f43793ac421717c60e0974950b0af2f3693b&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Now, to use a LLM there are 2 ways to do it, either you download it locally or use the API key of the model. Using the model locally could cause you storage issues when the model is big in size for ex- openAI, Anthropic etc.


now if you have to use more than one model for ex - Gemini, Anthropic, openAI etc. you’ll have to create a new file in the workspace with the name “ **.env** “. The work of this file would be to store the API keys of each and every model you’ll use. 

The next step is to make API keys for the models, for example if i am using the gemini api key the syntax for that which has to be written in the .env file will be - 


**Command for using API key through .env file :** 


GOOGLE_API_KEY = “write your api key here”


    Now, create two folders names as “CHAT MODEL’ and “EMBEDDING MODEL” because that is what we will learn in the first lesson.


    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/cfaaa527-7618-4958-85a4-ab38a390316c/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466X7NROP7F%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIFiCkyxN3qkiEc2tANYf8EkYWUVGM0FSj3T0mRoeLxRoAiEAmtuRpqOvWED5pbAmXtaYavL5PxsBLoY5BRaGn%2FrZMNsqiAQI9f%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDOXv7iqfEjIgJI7frircA4ZiCM%2Ff1OkZ4%2Bw8eymRTThn7gZUU%2FNlWCAxAjoQPjiX54dPTZzyt7hTl%2Bhvfd5F%2ByYmdOyJugBEFW7p6etWN54aYfX6l6yjT20vjx2eW%2BDAJCGtMY5ZU0eiX8q0mLQhw4BiPiI0cslPMDg%2F4yxqIgiBmJPzR4KiPhQ9lC0eQBZx3Jl%2FfoF4Nykf7eVjQadakGKW%2Bkf1uZWi7aaqQDYutnRpdPT7TYWH%2F5M2Evw5W36qw2JagLNDNFQ9a1a%2BpiRs%2BSb5z%2Fi%2BgoLev4e16CkgcpDpuBgwSooz4pEOjpSpJw6%2BgX99dH6M41rIOczU45oB%2F%2BNdRZZCfaJcVnC%2FXYNHz93MsByfiBs0KctcVrsIuERfdgh1Z%2FVHZhoF0PSBVSI36od2pZ5RRIh46SfcdK6%2BLpvgoiRtRK0LhOZUesGFDGbIyh9RlFFl0TRW0CVTyfJKTLhaeNyKIZi64RNFJWyosjxzAwxGgr8lf4CX8rI8zxMpVjxziLkj1kBCZ4rpY3u3r6ufEE8PLYLIoTeMaWFBRgWyR1rT%2FP%2BOtlgX7MK1Y9xIA5T0YTSX72%2FbTUesNH1sH5U%2BK2AKD0kuq%2F3Vanr7l2YdO%2BqxMtWC20JRNaPSwTBhhZgorezYwOYfYAuEMJ6dhNcGOqUB5%2FGRjhDSLIJXeTfLg4BV%2BDOBNGr5U6%2FImNTNlgIPgHMD%2BLyP%2BTpBDpK1GjB%2BDqX1BIuUNWp19Ra8rp7sfCPOvGb%2FXef6j9ydHvVOxgaXfS1l5E62BfJIk1yNAWqackP1TAI4KJ2V64JCL4b%2FCZhDdukazAfM%2FBg2b%2Bdq1MB%2BBS2mBXG%2FJtP7n86M4ipvjdDQJrNgwedDJVo1k8e01OFXUz4FQ%2F6J&X-Amz-Signature=53d32080de40e3e54187b2f5b997ea7ede6bcf0b42dcfab88312bc3622bcad23&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


To use the models we will have to download few data of that models locally as well using the API keys, for that make requirements.txt, in that ask chatgpt to make the things that you need to paste in the requirements.txt file, after pasting save the file using ctrl+s, and then in the terminal run the command listed below to download the data about the model so that you can use it - 


**Command for installing requirements.txt through terminal -** 


uv pip install -r requirements.txt


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/540ecfdc-351f-451c-8972-c1e3c809b8c9/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=2b36dd04d38e6c4226cf7194f96f75d7ea4adc0263468e2d5470a0fbd1c4a962&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


After installing requirements you can make a “chat.py” file in the chatModel folder and then in that file you have to write following things



![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/00d1dbfa-484b-40d2-8c59-87323aeb75da/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=3025b2247882d17a39bb027d79a7a8dc3c3c528d05316c04e85d0cf477a0e9b0&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


```python
from dotenv import load_dotenv
load_dotenv()
```


The above mentioned code loads the “.env” file which contains all the API keys so that we can use the models.


Then go on to the langchain docs and then go to Models section and copy the code for initializing the model which is as follows - 



```python
from langchain.chat_models import init_chat_model
model = init_chat_model("gpt-6-luna")
```


You can write any model’s name in place of “gpt-6-luna” based on the pricing you can afford from the LLM’s.


Then go ahead with asking a question as follows - 


```python
response = model.invoke("what is cricket")
print(response.content)
```


Now if you only print(response) the output in the terminal would be as follows - 


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/1f558927-1634-4b7b-883e-019853390848/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=85a3cfef7be420f96b934b1f8789554f218c9e7e983fb8df1e528677b040be4d&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Which is quite big and there are a lot of unwanted things in the same. So instead of using print(response) we use print(response.content) to retrieve only the content portion of the output which is as follows - 


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/d789602a-b03b-47aa-bc70-f8c1b7c11a0b/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=74103fbb448aa89d2cc9e3b83b3bbe4afb17d6dbe758275904a88f74a726d799&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Now if you don’t want to use “init_chat_model” and you want to use directly a specific model you can change your code to as follows - 


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/5955e82b-8a53-47b8-a360-6b84a2823282/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=5e776e4d90886e81b903df0168c08d114d129011297b5764b7d4120020b14a42&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


it’s upto you whether you wanna use init_chat_model or the Model Class. If you want to use any other model class you can retrieve its code syntax from the langchain docs.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/8a19986c-f83a-4415-9c1b-2aa19760af40/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=528fb58353127eb0e40e917ff39f58aabfae916f81a49a34486bc810624769d4&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


the above code contains parameters such as t**emperature** and **max_tokens** these parameters can be used ahead of the model name, the temperature parameters value lies within 0 and 1, as we go towards 1 from 0 for example 0.7 or 0.9, the answer starts getting more creative. Furthermore the parameter max_tokens value sets a limit of spending tokens and hence affects the output.


# Open source LLM (Hugging face) -


There are two ways to access a model, either use it’s API key which will again have token limitation, but if you want to use a model without any limitation you can install or download that model locally in your system providing you token-less unlimited access to its resources.


So first of all you need to install Hugging Face into your system, there are two ways to do it, you either add it into requirements.txt file as “**langchain_huggingface”** or you can use the command - 


**uv pip install langchain_huggingface**


in the terminal.


Then create the access token through the website and add it into your .env file. 


Now copy a repo id of any model from hugging face for example, I’ve chosen deepseek here


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/b18dfb5c-74b5-479d-bed3-b87598ae0cde/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=e77ed0d2467511359fa16cf0e679196203957e1fbb74a95bfb2e7899806700ef&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


the above showed is the repo id in this case.


After copying the repo id we’ll start creating the endpoint of the hugging face by declaring our own LLM with the command - 


**Command :**


```python
from langchain_huggingface import ChatHuggingFace, HuggingFaceEndpoint

llm = HuggingFaceEndpoint(repo_id="deepseek-ai/DeepSeek-R1")

model = ChatHuggingFace(llm = llm)
response = model.invoke("who are you?")
print(response.content)
```


which can also be found on the model docs of the langchain website. Remember the above method requires you to have paid tokens in your hugging face account for that respective model.


Now, to use the model without the use of tokens, you have to download the model locally into your system. For the very same purpose, we’ll use a small model because in general models have a huge downloadable content and size. 


You can directly download the local model through code only, for which you have to install transformers first, the command for the same is - 


**uv pip install transformers**


Also, install pytorch if you still haven’t in your system, for the same, run this command in your active terminal - 


**uv pip install torch --index-url** [**https://download.pytorch.org/whl/cpu**](https://download.pytorch.org/whl/cpu)


Now, go for the installation of the model, the code for the same is as follows - 


```python
from langchain_huggingface import ChatHuggingFace, HuggingFacePipeline

llm = HuggingFacePipeline.from_model_id(
    model_id="TinyLlama/TinyLlama-1.1B-Chat-v1.0",
    task="text-generation",
    pipeline_kwargs=dict(
        max_new_tokens=512,
        do_sample=False,
        repetition_penalty=1.03,
    ),
)

chat_model=ChatHuggingFace(llm = llm)
response = chat_model.invoke("What day is today?")
print(response.content)
```


The output produced for the same is:


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/fca6d429-ea29-425f-bdf2-9aa0c1666fe4/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=63aa88c3fe9ececeacb7eec3c96db4cf939029e7391167742f60188d8ef7c574&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


# Embedding 


Now we will move forward with embedding, embedding is a dense list of number(a vector) that translates human language into a mathematical format that a computer can understand.


for embedding, what you have to do is choose an embedding model first, in my case I am going with gemini-embedding-001, because it was available to use without purchasing credits.


Create an “embedding.py” file in the embedding Model folder you created earlier.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/e629bb7c-0d9f-4089-810d-39f91e4adaa9/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=b61f3f857c02ad4323934cc19d7c82bee813b21248a82e4971eae3972ce01648&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Then import the langchain requirement for the same and create an embedding variable to call the imported package with the model name and dimensions declared. (dimensions is the max limit only as it was in the case of chat model).


Then create a vector to use the embedding, which will have the command :


**vector = embeddings.embed_query/document**


You have 2 options to choose either the embed_query method or the embed_document method, the query method is used when you have a single line language that you need to be embedded, and document method is used when you have multiple sentences or an entire document that needs embedding. In my case as an example I'll use the query method.


```python
from langchain_google_genai import GoogleGenerativeAIEmbeddings
from dotenv import load_dotenv

load_dotenv()

embeddings = GoogleGenerativeAIEmbeddings(
    model = "models/gemini-embedding-001",
    dimensions = 64
)

vector = embeddings.embed_query("You are going to learn gen AI")

print(vector)
```


Make sure to import the dotenv package too, so that the code can use the google API key you provided in the .env file.


If you have to work with the embed_documents method, the code for the same is provided below.


```python
from langchain_google_genai import GoogleGenerativeAIEmbeddings
from dotenv import load_dotenv

load_dotenv()

embeddings = GoogleGenerativeAIEmbeddings(
    model = "models/gemini-embedding-001",
    dimensions = 64
)

text = [
    "How are you doing",
    "I'll learn gen AI",
    "You'll learn gen AI"
]

vector = embeddings.embed_documents(text)

print(vector)
```


# Prompt Engineering - 


In this, we’ll be creating a chatbot of our own which we will use in the terminal.


The first step is as usual, import the LLM package from the requirements.txt file and call the method for chatting. 


The next is to invoke the chatbot as we have already committed before too, and print the response, while keeping all in a loop, so that the chatbot can run continuously till you kill it yourself. 


Now even in this I want to introduce with a thing, in the above chat examples, we always used **“response.content”** to print the final result only. But in the case of a chatbot we wont be using **“response.content”.** Why? You’ll see with the example mentioned below - 


```python
from langchain_google_genai import ChatGoogleGenerativeAI

model = ChatGoogleGenerativeAI(
    model = "gemma-4-31b-it",
    temperature = 0.9
)

print("--------------welcome Type 0 to exit---------------")
while True:
    prompt = input("You : ")
    if prompt == "0":
        break
    response = model.invoke(prompt)
    print("bot : ",response.content)
```


See, how we have used reponse.content above, now I’ll represent you the output of the same.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/53c2c771-d8a4-463e-bdaf-a655ececda29/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=065ad83a85844b27b34d32a4bd03ec853103075697b2dc2fc2f1b8d2a980d702&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


In the output, **“response.content”** also prints the thinking process of the chatbot, which we of course do not want, so instead of using **“response.content”** we will be using **“response.text”** so that it only prints the text part and not the thinking part of the output too. The same is represented below along with the output.


```python
from langchain_google_genai import ChatGoogleGenerativeAI

model = ChatGoogleGenerativeAI(
    model = "gemma-4-31b-it",
    temperature = 0.9
)

print("--------------welcome Type 0 to exit---------------")
while True:
    prompt = input("You : ")
    if prompt == "0":
        break
    response = model.invoke(prompt)
    print("bot : ",response.text)
```


And the output for the above code is as follows


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/34f616c4-3e51-4bbf-98df-85282d650642/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=c1a56757482dc9df1ea0b204e05c0dff99d9e7df3c2d4f00bbaac32f54e6c898&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Now, our chatbot right now does not have the feature of saving the chat history or we can say does not have a memory. Now you might think that we can implement a list that store all the chats and henceforth contribute by being a memory, but what if the person chatted for very long time?? the space complexity will keep on increasing only. So to solve this langchain introduced the method **“messages”**, which has three types - 


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/f6612d7b-c834-4e4b-a184-9b6759e428eb/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663KWQBULC%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJHMEUCIQCVLaZVfHnHUeyMV48oii%2FtHXR1My9TxmUkXcTsHiQQhAIgQ3r7nOEqXUMwA0tX0UZtfTWzYUlkNDoQh8nm0ZeYO%2BkqiAQI9v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDN%2FHkCPWlLt%2Fg%2B3QiircA9ygem3mInCshHG7mL2JTC44ZUV%2BThj3fiQa%2B2oxYf8XJCsR4BIEA5GQV9Ct%2FNY7PkSpTqWf%2Bfg0R0on7HlIRyH9sBt7YhLQP%2FVxOPkhCDbyvnOORrJ05gjJUS7ut3L9D6feqOSBoQ7sAl6ZXhFfeJTn3QSQTYvzHpudQYAcGKuTUNo6m%2BcTnlnIswTmtzRy44vmDq%2BHX6wdPtMDOTABaHtrIiEzQbYwsn3o4UJDBf0OZzdaA98Qs3XaVKBN6W%2BrBx01fLrcGcQplMYVfPJpMceTFIoN4WJpmFslUa2Evz2RctgT68K19D40f6xBc5k8O1Thlp1jnSz578NNoq55wJiqWd1KT3nCXhwndcK6tQTjxVIAOx5j9g2huzr0HUAjf%2F7ERI%2FxXpywG567kc05dzUXT2DkoaIb%2F5ZVb%2Bqihi9cbpbjcHBrIxkBJBx84g%2F58DU7sPC4%2BUZuz%2B8jYvwjMvbK4xivMrasfhDLMYWMFeAidshQM%2BPflLmgQwf2DC5I56DXppO7q66TWmZLql1z6d78i9nRn36x8QWH3dIz3p2vUKXBnL%2BrHjY6uZK6GACHIcr2FhmVLuQlXGZmwBUclHgXu6Td8YKU5er6enzyoAkeUUITxBUagEiLayKeMI%2BbhNcGOqUBkxLBDR1gl%2BX2zjppPGrBxZ%2BtHvLSam345fVFFgnNvIarp4tj4Sg2YQKgmVdjoPC38IfoKHOVMyLgg8Igeoidw4hF3nbRXvTrQDInUfxwtUPvECAMf3O19GSF0yLO72v0N2bomkr2R8kQepiGwiP1%2Ff8z%2Bpj5UytrBsG6dcFOtzGkTedhgUoJPjkSi%2FFY83z1k2LW%2BTHhRnsBZSTkawNHyWqHkZ4c&X-Amz-Signature=bb909a1fffbfb7a64bafaa4a0d6ad583e124abb81a705e63178ff8b76b5ed7f7&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/71eae7a4-1b02-4a76-8f4f-378ebfeee366/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466VXHWBCWQ%2F20261027%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261027T230146Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEC0aCXVzLXdlc3QtMiJGMEQCIC7tRBYDwa8JXWQ1UMXPgNK8OzKUqc%2ByQHhq%2BJeQuXCxAiBcijTE1HKGwP9SgcfjPerxOnzhQoRkCCBvyQ9Uwcb9OSqIBAj1%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F8BEAAaDDYzNzQyMzE4MzgwNSIMp1MOvHI7uTjvZr85KtwDOBErh9FOClkB9NsL2X7%2F9vHda35XayTAKdvV11Ym68TeEC8i0I7xPCWcVT%2FpNUvv4uokqCQNhAoHNke1iAtlTEFcCr%2FzSLpPDXcB5WoSx71vpirWSL0gsLIJksp9DLpXUiAWAz87wLRym4ANcjClwxPxJyRETL%2Bw9RKiaxVpQtcdzXlh3%2BiqxFhukCayjbsG8ZnK3xKj1Un%2BCavYAyPl6Z2f9iQV2Fc%2FqKmLynb2tlG%2FOjgrDYGgi77TFiCAR0xtENXWOhe8YxZcehrZOxB5sOAySWUHEfq25AO7aOX2mKFhkANsGkHtRto9wmCZhNp5V7VUoAKC46frZYF3V1qZARQhFhnqxUVIAuByLWuwh0EKUlIqJrS79LnEdsM5KeQEEreZ%2FMFnE01HssP6%2BIEZzK4qILw1mVu6El1usloD10NgCg83mAaIyBKL9JfuRRQsScrKmE5OruQGOoW4%2FIAdP%2BMfS3%2FBNGSsKc7yzUBwtKXKy03IejZS5bqVXNXpMMCtYYWseX76%2Fo8H%2BO0tYr5WCo94QB4Jovrzuqrh79LJ8IvmSAaHsjKHFck5ZIltvVU2ghEn4vwg%2F32gZY%2Bv9eH7JDR%2FMzNpQ9ElMlRB2DzTfkNJdyg4lHkLy5i2218wkpuE1wY6pgGaFEXuAiKJ%2BOwNx02MpSAOPThX%2F5iIAVf9KJWCh6JD9X%2FWNuJYf3B6AzSGKVnlZ6ilBcQCMGVdOgeBO4edSSd2Thorbgxa85c8bGIM%2BCmjzmhHShe4NCk6GLA%2BYLEaFOHF%2FgQhigICIoV%2BTsAqBKY5yOHvMshMVBMh43hzYTgRzN%2B%2FfX8cYq5UMQOdfQAKcWRQGGjq2PwBILaKXbPu8DcmLWwmByeX&X-Amz-Signature=9a2a26b0b1308f73c9f25f6e38799baae1d0fc249ed247473294e76939c4bbdb&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Now we will use all the above mentioned methods to store the message history in a way that it doesn’t get confusing at all. The code for the same is provided below - 


```python
from dotenv import load_dotenv
load_dotenv()

from langchain_groq import ChatGroq
from langchain_core.messages import AIMessage, SystemMessage, HumanMessage

messgaes = [
    SystemMessage(content = "You are a funny person and creates jokes.")
]

model = ChatGroq(
    model = "openai/gpt-oss-20b",
    temperature = 0.9
)

print("--------------welcome Type 0 to exit---------------")
while True:
    prompt = input("You : ")
    messgaes.append(HumanMessage(content = prompt))
    if prompt == "0":
        break
    response = model.invoke(prompt)
    messgaes.append(AIMessage(content = response.text))
    print("bot : ",response.text)

print(messgaes)
```


The print(message) in the last is specifically given so that you’ll be able to see the categorization of human, system and AI messages separately.

