DayZ "Pernicek Ginger Bread Man" Mod For PC Additional XML Snippets Instructions & Terms Of Use

When used with a correct instalation of the Pernicek PC Steam Mod by Hunterz ( https://steamcommunity.com/sharedfiles/filedetails/?id=2898679826 ) 
these snippets will spawn in Gingerbread Men as food in various locations around server. When thrown, the Gingerberad man
will turn into an infected Zombie and attack. I have also included xml snippets to spawn gingerbread man zombies with normal zombie groups too, and to give him some cargo.

Limited Testing on PC Chernarus Local Server DAYZ Version 1.19 Dev 2022.

XML Snippets Created by @scalespeeder. Please report bugs & errors to scalespeeder@gmail.com with screenshots.

TERMS OF USE
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS
OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN
AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH
THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Using these modded xml / json files and instructions could break the functioning of your DAYZ server, requiring a reinstall that would wipe
all player progress.

Using these modded files neccessitates increased regular restarts to prevent server crashing.

It is suggested you thoroughly test your server after applying these files to ensure proper
functioning of your server.

I always recomend you validate your files at: https://www.xmlvalidation.com/ and https://jsonformatter.curiousconcept.com/

Instructions:

Install the Pernicek on your server as you would any other DayZ Steam Mod for PC.

This snippet should be inserted into your types.xml (so the Gingerbread man spawns as a food item around your server):

<type name="Pernicek">
        <nominal>20</nominal>
        <lifetime>14400</lifetime>
        <restock>0</restock>
        <min>15</min>
        <quantmin>-1</quantmin>
        <quantmax>-1</quantmax>
        <cost>100</cost>
        <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
        <category name="food"/>
        <tag name="shelves"/>
        <usage name="Town"/>
        <usage name="Village"/>
        <value name="Tier1"/>
        <value name="Tier2"/>
        <value name="Tier3"/>
    </type>

  <type name="ZmbPernicek">
        <nominal>0</nominal>
        <lifetime>1800</lifetime>
        <restock>0</restock>
        <min>1</min>
        <quantmin>-1</quantmin>
        <quantmax>-1</quantmax>
        <cost>100</cost>
        <flags count_in_cargo="0" count_in_hoarder="0" count_in_map="1" count_in_player="0" crafted="0" deloot="0"/>
    </type>
	
	
This code snippet should be inserted into your events.xml file (to have the Gingerbreadman spawn with regular zombies):
	
	  <event name="InfectedVillage">
        <nominal>50</nominal>
        <min>25</min>
        <max>100</max>
        <lifetime>3</lifetime>
        <restock>0</restock>
        <saferadius>100</saferadius>
        <distanceradius>50</distanceradius>
        <cleanupradius>100</cleanupradius>
        <flags deletable="0" init_random="0" remove_damaged="1"/>
        <position>player</position>
        <limit>custom</limit>
        <active>1</active>
        <children>
            <child lootmax="5" lootmin="0" max="0" min="7" type="ZmbF_JoggerSkinny_Blue"/>
            <child lootmax="5" lootmin="0" max="0" min="6" type="ZmbF_JoggerSkinny_Brown"/>
            <child lootmax="5" lootmin="0" max="0" min="7" type="ZmbF_JoggerSkinny_Green"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbF_MilkMaidOld_Beige"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbF_MilkMaidOld_Black"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbF_MilkMaidOld_Grey"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbF_VillagerOld_Green"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbF_VillagerOld_Red"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbF_VillagerOld_White"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbM_FarmerFat_Blue"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbM_FarmerFat_Brown"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbM_FarmerFat_Green"/>
            <child lootmax="5" lootmin="0" max="0" min="6" type="ZmbM_Jacket_beige"/>
            <child lootmax="5" lootmin="0" max="0" min="6" type="ZmbM_Jacket_black"/>
            <child lootmax="5" lootmin="0" max="0" min="6" type="ZmbM_Jacket_blue"/>
            <child lootmax="5" lootmin="0" max="0" min="6" type="ZmbM_Jacket_brown"/>
            <child lootmax="5" lootmin="0" max="0" min="6" type="ZmbM_Jacket_greenchecks"/>
            <child lootmax="5" lootmin="0" max="0" min="6" type="ZmbM_Jacket_grey"/>
            <child lootmax="5" lootmin="0" max="0" min="6" type="ZmbM_Jacket_khaki"/>
            <child lootmax="5" lootmin="0" max="0" min="6" type="ZmbM_Jacket_stripes"/>
            <child lootmax="5" lootmin="0" max="0" min="5" type="ZmbM_JoggerSkinny_Blue"/>
            <child lootmax="5" lootmin="0" max="0" min="5" type="ZmbM_JoggerSkinny_Green"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbM_VillagerOld_Blue"/>
            <child lootmax="5" lootmin="0" max="0" min="2" type="ZmbM_VillagerOld_White"/>
			<child lootmax="5" lootmin="0" max="0" min="2" type="ZmbPernicek"/>
        </children>
    </event>
	

Add this code snippet to your cfgspawnabletypes.xml (to added some cargo to the Gingerberead Man):

	<type name="ZmbPernicek">
		<cargo chance="1.00">
			<item name="PunchedCard" />
		</cargo>
	</type>
	
Save and re-upload if necessary and re-start your server for the changes to take effect.

Thanks, Rob.