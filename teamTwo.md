---
layout: default
title: 'Team 2: Data Mapping' 
nav_order: 3
has_children: true
permalink: /teamTwo
---

<h4>Docker</h4>
<ul style="list-style-type:disc;">
    <li>Setup Docker  <a href="https://github.com/code-openness/pik-wikibase">as shown here</a>  </li>
    <li>Start Docker</li>
    <li>docker-compose up</li>
  </ul> 

<h4>Bot Password</h4>
                                    <ul style="list-style-type:disc;">
                                        <li>Open and login to Wikibase in browser (address, username and password are specified in docker-compose.yml)</li>
                                        <li>Go to Special Pages -> Bot passwords {address}/wiki/Special:BotPasswords</li>
                                        <li>Create a bot named bot, check all permissions and click create</li>
                                        <li>Copy the created Password (it should look like this: bot@7f7fqvfd5v5mn0nb7v214pu8vtj2vif8)</li>
                                      </ul>  

<h4>Clean Up</h4>
                                        <h4>To completely delete the data from your Wikibase instance follow the instructions:</h4>
 <ol>
                                            <li>In the console, in the folder where your docker-compose.yml is located, run <br> docker-compose down --volumes <br> to delete all data from the database and other data related to Wikibase</li>
                                            <li> In the console, in the folder data-mapping run <br> rm -rf apicache-py3 && rm -rf import_env && rm -rf pywikibot.lwp && rm -rf user-config.py&& rm -rf import.py && rm -rf data && rm -rf password && rm -rf throttle.ctrl && rm -rf <br> to delete the temporary data <br> Now you have an empty Wikibase instance again.</li>
                                          </ol>

<h4>Requirements to run code</h4>
                            <ul style="list-style-type:disc;">
                                <li>Python 3.7.x</li>
                                <li>WikidataIntegrator</li>
                                <li>Pywikibot</li>
                              </ul>

<h4>Wrote a code to add all items in Wikibase</h4>
                                        <ol>
                                            <li>Properties must already be present in the Wiki
                                              </li>
                                            <li>Get a .CSV file as parameter </li>
                                          </ol>
                                          <p>
                                              After successful completion of the script 2 files should be created:
                                          </p>
                                          <ol>
                                              <li>csv_path_updated.csv
                                                </li>
                                              <li>csv_path_errors.csv(contains all successfully added items with newly created QID)</li>
                                            </ol>
                                            <p>
                                            Important parts of the code:
                                            </p>
                                            <ol>
                                                <li>Open CSV file.</li>
                                                <li>Go through all items in a loop.</li>
                                                <li>Compare type of item with data type from wiki and add accordingly.</li>
                                                <li>Save added items with QIDs in a new file.</li>
                                              </ol>

<h4>Wrote a code to add all Properties in Wikibase</h4>
                            <ul style="list-style-type:disc;">
                                <li>Received a .CSV file as parameter</li>
                                <li>Adds all Properties to Wiki </li>
                              </ul>
                              
  <h4>Then we specified that the code(items and properties) can be more efficiently written in a file.</h4>
<h4>This program contains these files:</h4>
    <ol>
        <li>base.import.py: adds a new data model to Wikibase.</li>
        <li>base.user-config.py: contains user information.</li>
        <li>requirements.txt : contains all requirements to execute the code.</li>
        <li>import.sh : contains commands to execute the code.</li>
      </ol>
     <div></div>                       
    <h4>Executing the script</h4>
                                    <ol>
                                        <li>Clone the <a href="https://github.com/code-openness/data-mapping">data-mapping repository</a>  <br> git clone git@github.com:code-openness/data-mapping.git </li>
                                        <li>Open data-mapping/import.sh in editor  </li>
                                        <li>Paste your bot password <br> export BOT_PASSWORD=bot@7f7fqvfd5v5mn0nb7v214pu8vtj2vif8  </li>
                                        <li>Adjust MEDIA_WIKI_SERVER with the host address from your docker-compose.yml file <br> export MEDIA_WIKI_SERVER=http://localhost:8181</li>
                                        <li>Adjust SPARQL_ENDPOINT with the host address from your docker-compose.yml file <br> export MEDIA_WIKI_SERVER=http://localhost:8181</li>
                                        <li>Save import.sh file</li>
                                        <li>execute import.sh  <br> ./import.sh </li>
                                      </ol>
                                      <p>Then we tried to make the code perform better through multithreadding.</p>                         
                             
                             
