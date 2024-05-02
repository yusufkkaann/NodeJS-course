2: Blog oluşturmaya hazır mısınız? Konsol ekranında postlarımızı sıralayalım, sonrasında yeni bir post oluşturalım ve yeni post ile birlikte postlarımızı tekrar sıralayalım.

--------------------------------------------------------------------------------------------------------------------
const teams = [
  { name: "Fenerbahçe", country: "Turkey" },
  { name: "Real Madrid", country: "Spain" },
  { name: "Manchester United", country: "England" },
];
function listTeam() {
  teams.map((team) => {
    console.log(team.name);
  });
}
// listTeam();
const addNewTeam = (team) => {
  const promise = new Promise((resolve, reject) => {
    if (team) {
      teams.push(team);
      console.log("------Takım eklendi------");
      listTeam();
      resolve(teams);
    } else {
      reject("Takım eklenemedi");
    }
  });
  return promise;
};
async function showTeams() {
  try {
    await listTeam();
    await addNewTeam({ name: "Barcelona", country: "Spain" });
  } catch (error) {
    console.log(error);
  }
}
showTeams();
--------------------------------------------------------------------------------------------------------------------
