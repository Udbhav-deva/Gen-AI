
 


# LangChain, LLM’s, Prompt Engineering


Open VS code with a new workspace folder and then open terminal in it. 
We will first install UV in through the terminal, with the command for windows as - 


**Command for UV installation in windows :**


powershell -ExecutionPolicy ByPass -c "irm [https://astral.sh/uv/install.ps1](https://astral.sh/uv/install.ps1) | iex"


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/e4c3cec8-5843-4603-a630-258d940905b2/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=9fcb60f62a255badef4907dca7e4416a85ed859f8619c823af20fb2ee805b62e&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Then comes the step of creating an environment and activating it, the command for creating an environment or a virtual machine is - 


**Command for checking the UV version and creating a virtual environment :**


uv  - -version  (remove the space between the dashes in the terminal) 


uv venv  (for creating a virtual machine)


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/829e0b51-f98c-4c60-b2db-7321059aca9c/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=943c83741fd1b604a4bb32d552e057e47fb66c980b58f69e9e80de2c8e28e947&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Then you have to activate the virtual machine using the same command you can see above in the “Activate with: .venv\scripts\activate”. The command you have to put in the terminal would be whatever written in your terminal after the “Activate with: “ statement, as in my case the command would be : 


**Command for activating the virtual machine :** 


.venv\scripts\activate


Once the activation of the virtual machine is done, the next step includes setting up the VM or the project and adding langchain into the system - 


**Command to set up the project/VM :** 


uv init  (this will create a .toml file in your sytem)


**Command for adding langchain -** 


uv add langchain


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/17ea5185-3b80-4d08-9a3a-32e50948284d/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=b6c23d98820ebf39b6d77dcabc8026392e4b2e6cdd6311e2ca59acf8d6e8f13b&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


now to check whether langchain has been installed in our sytem or not, make a new [test.py](http://test.py/) file and run the following code prompt


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/ee721c0f-f2f9-43bd-b851-714c018c4c75/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=0318aa47002386b11e5c2fc7c68c994dabb07d54e56d9835940a8c0f3cbb3a1a&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


which will produce an output as such -


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/6f17f668-2e1e-4375-958f-1add5cad43c9/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=e67290d9640ec7c1814d64d1c56abfa0260eef0451147777933077d296f3d5e5&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Now, to use a LLM there are 2 ways to do it, either you download it locally or use the API key of the model. Using the model locally could cause you storage issues when the model is big in size for ex- openAI, Anthropic etc.


now if you have to use more than one model for ex - Gemini, Anthropic, openAI etc. you’ll have to create a new file in the workspace with the name “ **.env** “. The work of this file would be to store the API keys of each and every model you’ll use. 

The next step is to make API keys for the models, for example if i am using the gemini api key the syntax for that which has to be written in the .env file will be - 


**Command for using API key through .env file :** 


GOOGLE_API_KEY = “write your api key here”


    Now, create two folders names as “CHAT MODEL’ and “EMBEDDING MODEL” because that is what we will learn in the first lesson.


    ![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/cfaaa527-7618-4958-85a4-ab38a390316c/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB46657MKXTB6%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJIMEYCIQDQ9s6qnKoaewvdXzSWK%2BjhgFoVzLHLf8Y8VtfPaqZ%2BKwIhAPEpUGx2HtnPhQelPpH%2FEx5yvyLdmgVdRUOcpde9Wy5gKogECPr%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEQABoMNjM3NDIzMTgzODA1IgzAi%2F0oTS1vU%2FOiyesq3ANDacj14uAqD1OEkHWFREm0KtUfj0EuTBmJsb5KZM3UAe%2BqZrEGC4XEjegHehaAohhM%2BNeCrpN%2Bk5qnLz54WrgYMckO4OWMHYX6mM%2BO7gQ7MaLO5fg%2FsCRgtGbuMJzWpV3Z6tr3vN9WwTHeSBizQequ%2BM1tcgnjZW4%2B7z8b2eIVN%2FePRok%2FjY4b3fOsvXXvhpGPYxVp4ktJPbzw%2Frl%2B8YVZJB8kn4SEwmSBVAZ2%2FXgTWsnezD1taSn24X74Au2Lm8KqvYM9OOXDlQOFEaScyG0Z18h1jN%2BTUN5EjK%2BcXr5M57%2BAsLNqlyUvChapk9xK%2FH3sDjDQoVB1xsZmlceTFSf996r9zzl3kcgwMfGUzFQTUAAY3j9kXa%2Fx3%2BjPsfthxtuWE6T9SjA2XR8CatlJCKSoprp6%2FizYqXpYGDa5D57NzbTZysOaz4i26uqMDrlT7DDWPjeyEMCwayaUJxEvKr%2F37i%2Fvm01INHChpVHXrtihdHdZmjM7DbUaRvpryStVUtx%2B7gIpgynKwfS9g057INsfR7hVorzvpSRPAqdx2MpQsVBPQfeD8WUiy9qsJkU8g1ccUxENry%2FIl%2BFiTsxXexDcKIhuoKqFDN%2B2EQIOwjV2V6xuL6h3VzMatU2ugzChsYXXBjqkAaDuAHtPzu8a8QwWv5dz2CAKBRZqMf%2Fw61gts8bJePaE2EP1G%2BnT4ubjj75W0NobsGkInaQ5k%2Bt2uVWrHIWJiX3ZqGICHJ5D%2FbKOSig6ALZfn4R2e2o3G7TtVqcItCyqHeJzL9J0A4jURm277EdJjGHDZaVZ5CseQ6hA%2BMaENtbp%2Fjdj3NK92OrYIl5gTmx81VDY0pdDLKvnb51iH0MRysFmeSxv&X-Amz-Signature=37aa643fe322839cb2ceda3e161a40632a88d134cea5b16171bc6db459dea14f&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


To use the models we will have to download few data of that models locally as well using the API keys, for that make requirements.txt, in that ask chatgpt to make the things that you need to paste in the requirements.txt file, after pasting save the file using ctrl+s, and then in the terminal run the command listed below to download the data about the model so that you can use it - 


**Command for installing requirements.txt through terminal -** 


uv pip install -r requirements.txt


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/540ecfdc-351f-451c-8972-c1e3c809b8c9/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=db34ecd408252b441932d7899adcb1a1c802c4d49361f3084de4a8f8c85fe954&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


After installing requirements you can make a “chat.py” file in the chatModel folder and then in that file you have to write following things



![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/00d1dbfa-484b-40d2-8c59-87323aeb75da/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=01fa32172106b84779a173321a2a37b33d1d8c3624874f3a61ddb980ab6b6dbc&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


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


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/1f558927-1634-4b7b-883e-019853390848/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=e67475bee58b398e787e486ed80b02b1bbf94dedd2ac03e1a0033bf11726a45d&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Which is quite big and there are a lot of unwanted things in the same. So instead of using print(response) we use print(response.content) to retrieve only the content portion of the output which is as follows - 


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/d789602a-b03b-47aa-bc70-f8c1b7c11a0b/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=28219d7d62bad5f49d7828387e311c7b2ec087890350e8c1f2b1c6dcda8ffcc8&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Now if you don’t want to use “init_chat_model” and you want to use directly a specific model you can change your code to as follows - 


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/5955e82b-8a53-47b8-a360-6b84a2823282/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=b9e5d88bffca89bbb6f4dcc2d6f88626e608bae98b6bc1e4ae5235d27a77f50f&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


it’s upto you whether you wanna use init_chat_model or the Model Class. If you want to use any other model class you can retrieve its code syntax from the langchain docs.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/8a19986c-f83a-4415-9c1b-2aa19760af40/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=893d7cb9cea49d8149091158f7bba5874df10c64b6ed35e59a5ae3839f7d45cc&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


the above code contains parameters such as t**emperature** and **max_tokens** these parameters can be used ahead of the model name, the temperature parameters value lies within 0 and 1, as we go towards 1 from 0 for example 0.7 or 0.9, the answer starts getting more creative. Furthermore the parameter max_tokens value sets a limit of spending tokens and hence affects the output.


# Open source LLM (Hugging face) -


There are two ways to access a model, either use it’s API key which will again have token limitation, but if you want to use a model without any limitation you can install or download that model locally in your system providing you token-less unlimited access to its resources.


So first of all you need to install Hugging Face into your system, there are two ways to do it, you either add it into requirements.txt file as “**langchain_huggingface”** or you can use the command - 


**uv pip install langchain_huggingface**


in the terminal.


Then create the access token through the website and add it into your .env file. 


Now copy a repo id of any model from hugging face for example, I’ve chosen deepseek here


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/b18dfb5c-74b5-479d-bed3-b87598ae0cde/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=9c2f1d6d1406bfc8d2c7e20d86a6d5843ee238da6d13b243e3b5497b3b954d48&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


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


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/fca6d429-ea29-425f-bdf2-9aa0c1666fe4/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=273371a3df66df2d8dc4a68d0fa357d88769fb85545f6e7116d1381ab83fa7d1&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


# Embedding 


Now we will move forward with embedding, embedding is a dense list of number(a vector) that translates human language into a mathematical format that a computer can understand.


for embedding, what you have to do is choose an embedding model first, in my case I am going with gemini-embedding-001, because it was available to use without purchasing credits.


Create an “embedding.py” file in the embedding Model folder you created earlier.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/e629bb7c-0d9f-4089-810d-39f91e4adaa9/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=5df9d78ba435357bb5eb832a9d98229b0aa1d3d640bb6c4b01758c083a91a2c5&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


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


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/53c2c771-d8a4-463e-bdaf-a655ececda29/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=6dd46f44391de4a3e7213c7730d60b2929949de63d47647c30669692943b8c6f&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


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


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/34f616c4-3e51-4bbf-98df-85282d650642/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=1faf4597ff42a428eaff47828faf069e7e17d1e1898a249a4327060cd5d46d8d&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


Now, our chatbot right now does not have the feature of saving the chat history or we can say does not have a memory. Now you might think that we can implement a list that store all the chats and henceforth contribute by being a memory, but what if the person chatted for very long time?? the space complexity will keep on increasing only. So to solve this langchain introduced the method **“messages”**, which has three types - 


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/f6612d7b-c834-4e4b-a184-9b6759e428eb/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4662B46Z2NI%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIQCiwfOc5OCxjADC5Bmjb8INLCjpHFEavYQtJcKgdELwBgIgFVQHvefOfj4bSEv9F7ls7aipJE7iI4boDqNrKUOaomUqiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDKIHwUf7daJW1vDF3ircAyoZjK4A0tYkM0ypZk04MPDhvjLgxZNWsA9yaofHPMT47S23Fr2sDyp%2FfzjH9im7GKRWFOPe3unkwilpIcX9FXeJbKSUXSQyEkmqdbuwqv3ZRyR7pwFJu8eBegSK1NTDsBSNcLNskOM2Fp%2BnK1fq9cP%2FFM9%2B79oP9gAAXIjhjUKdj1CT8yLsrj70aZBXxrD2HW9%2Bb7fWxsstRWGqhpCftEK1OoeMyhXH64Eh%2FAJIty%2BuAL40gGfslSan%2Bnj3eEeKKLGU4Qe771cJ8AxZeitAh5bgemABG2UAnfumkzSFpnwSPCcTeka2aSRpIg7Ar5BkxdSjZZr4ItX0qcP4pl6fka5QD99ZR%2B5VpYuILwjn%2BTSm2I7SAeuMBNukJlYzDXQusEd8FpcNDav2Od04fCYqgPHQM4XlHa%2B3fraJ8CmCqulp2NyCk5q1HTNEByCEZm%2F6tS3eCeXssPo9teJr0r8HIW3FZCaMiBckmTr%2B3HArwDRia6c6SeCNp%2BOp%2BG3KIUpiTQdGhY7RHTutyyI2VP92Rti1FNL3jxZqgAAKV1w7wW%2BYWFLoHmEWPUhfxnn2diAa6elTsOtfLPQe2UI2eLoME%2Bgf43FaBNN%2FC4oNQXhCKmig85UfTb8Sa8bpUa%2FUMMOzhdcGOqUBc3JJWTl0DDmi4pNzJf4w7qLCPf06ot%2Fvw0LtnZZiHAfLNBOi%2BoaTIjGBMKmYz2Qc0woLGtCE9cKM%2FsAJyfLoFb5C740WHTSiBaDBs5pcFcqsPNB0rardKWiz%2Fi%2FKEcrmEADWpE7k9qdAa42%2BYThn4GBV3OFpVd%2FuMWVhKjySFzfnf1uN8vlv%2FpYgo3Hd7a0SjyXWYmo1aLB1vjAnrlLxxYuxpIxS&X-Amz-Signature=d073bfc471a4b13ab8e8ce78fea37eea8e82c92c759bcba2939f7b499e63ad1d&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a59e2f63-c65e-8182-a057-0003b1311564/71eae7a4-1b02-4a76-8f4f-378ebfeee366/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4666W35LD5X%2F20261028%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20261028T032638Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDIaCXVzLXdlc3QtMiJHMEUCIH84%2F%2BlvZ7lhfQwya70p%2FWUV7tiZL91jUuWFuoZ1icSyAiEArtjFSsogXWGE4NyBBUYArE0bnV%2BqCzNcj1GuB%2BV2Ez0qiAQI%2B%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDM7izSJ0hw1Z3MiAnircA7QA5fl0TTBf7IIt7hdWiNg57nl5b89e%2FWAJxJfCZbWGQCVUY%2BjKLU1tdxuvaQ0BkQsWkS9rA5X1sCOxP7uTvqf7R7pQMQu3SW8tkcBe9S5V5Xjimbb00Uz%2F0R9IuslOHTNQ%2FYswVTspKc7opOmdBH5ixBRg5l6WYFgg6%2BVXTTvjwIyz%2FldcgxNiKa7npX2t817XcuF7vGyYgt7UpQ2K8N%2BmuXWwb3iG4HqfCaZ4FvRKbtX%2FbhnvQKPbpFbLA%2BwLbGxIrY%2BZPDI8cB0b8fxzsTLoMZBjh6OSqZnB71j6pouU6CLc%2BoIxz%2BlORWo7gkflu9JFtzMKsPf0z1Q0QNIxnB%2Fb5Y8ziZcg48UArjvI7eYLoxeylZX2S9QHQoqbxW5Ot2tN8cBEdwaXAT1%2Bb%2BtwuuxDlSyMyj10CT5wXCtvTv1XCu3O0tvcyH3meeNTFX2HEtSYIayu4VY6Gn%2BMWhw8EsrqQJ1Y9EL0gz0KTBJgre7FhmP2w2wk30h353fh%2FU0gYL4Qtf0VMIK8kAMg%2Fe444yWy16aDpj4TXZ%2BOciyN%2F7Ft%2FxJqK2hNFLL3HtMx9hhW0Y7xV8N7fGFBS2niqaku4ybPTmKChfe1jl%2FxLnM0PJAcsfIjbelrjuE3tkbwMKqzhdcGOqUBe1LdxMK0TpDTqSS0EaO3Bf43%2B88sCUCim0F7vtFbmM9vu3lvjV2vpW%2F5oZVe191lE5OTCaYxmZp3bzQwwG%2BbVBSYsgStws4KRL9%2BZ9HwcJtJGr%2B4mfuNfaWTYfzj2%2BphNbAWfkYnaWG7uBiJF2wSvgACX1v1emr61Qh9akIMPHusH0oHJ093SJ50lyBCdcApV8jeKMMGrbU43xDdJihsKnnD%2BqDy&X-Amz-Signature=8a1f4ce5e94e287c23663bec0c3cee1c0cf8cc706a027c93bbb72849db7241a0&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


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

