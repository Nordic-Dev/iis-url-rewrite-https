# IIS HTTPS Rewrite Rule
Automatically rewrite requests from http --> https in .Net websites add this url rewrite rule to your <rules> in the web.config.
  
  ```
 <rules>
	<rule name="HTTPS" enabled="true" patternSyntax="Wildcard" stopProcessing="true">
		<match url="*" />
		<conditions logicalGrouping="MatchAny">
			<add input="{HTTPS}" pattern="off" />
		</conditions>
		<action type="Redirect" url="https://{HTTP_HOST}{REQUEST_URI}" redirectType="Found" />
	</rule>
</rules>
```
