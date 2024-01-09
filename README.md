import inquirer from "inquirer";
let todos: string[] = [];
let loop = true;
while(loop){
    const answers:{
        TODO: string,
        AddMore: boolean
    } = await inquirer.prompt([
        {
            type:"input",
            name:"TODO",
            message:"What Do You Want To Add In Todo List"
    
        },
        {
            type:"confirm",
            name:"AddMore",
            message:"Do You Want More In Todo ?",
            default: false
    
        }
    ])
    const {AddMore,TODO} = answers;
    console.log(answers)
    loop = AddMore
    if(TODO){
        todos.push(TODO)

    } else{
        console.log("Kindly Add Valid Input")
    }
    if(todos.length > 0){
        console.log("YOur Todo List: \n")
        todos.forEach(TODO => {
            console.log(TODO)
        });

    }else{
        console.log("No Todos List Found")
    }
} 
console.log(todos)
