# Developer guide
## Cypher and BNF
If a valid query is not syntactically recognized, 90% chance the problem is in **Cypher.bnf**.  

Use the PsiViewer IDEA plugin. Run project, go to Tools->View PSI Structure, paste your query, click "Build PSI tree"  
and analyze the tree. Once you spot some errors, compare the tree to what it should look like, based on Cypher,  
and try to find out where exactly some changes must be made in Cypher.bnf.  

After editing the .bnf file and making sure the query is parsed correctly, right-click the bnf and **Generate Parser Code**.  
Run all tests via the Gradle task (_jetbrains-plugin-graph-database-support/Tasks/verification/test_) and start fixing tests.  

To fix integration tests where the PSI tree does not correspond to the expected one, check the tree that is printed out  
and replace contents of the corresponding .txt file with the tree. In some cases, the query itself (.cyp) should be corrected.