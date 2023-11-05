# 作業2


https://github.com/zhaohongg/yzu-swiftui-1101453/assets/149959884/9d31db86-2e72-4d73-9d13-0eba174f2ac7

## c
```swift

import SwiftUI

struct ContentView: View {
    @State var cpu:Int = 0
    var cpuImage = ["Rock", "Scissors", "Paper"]
    @State var gameOut = ""
    @State var point = 100
    @State var money = 50
    @State var runTime = 1.5
    @State var timerRunning = false
    @State var timer = Timer.publish(every: 0.1, on: .main, in: .common).autoconnect()
    
    
    var body: some View {
        ZStack{
            Rectangle()
                .fill(Color(red: 100/255, green: 205/255, blue: 203/255))
                .frame(minWidth: 0, idealWidth: 100, maxWidth: .infinity, minHeight: 0, idealHeight: 100, maxHeight: .infinity, alignment: .center)
                .ignoresSafeArea(.all)
            VStack{
                Image(cpuImage[cpu])
                    .resizable()
                    .scaledToFit()
                    .frame(width: 250, height: 250, alignment: .center)
                    .offset(x: 0, y: 20)
                Text("your $: \(point)")
                    .font(.system(size: 50, weight: .bold))
                    .foregroundStyle(Color.brown)
                    .opacity(0.7)
                    .offset(x: 0, y: 50)
                Text("\(gameOut)")
                    .foregroundStyle(Color.red)
                    .offset(x: 0, y: 70)
                    .font(.system(size: 50))
                HStack{
                    Button(action: {
                        timerRunning = true
                        cpuRandom()
                        checkWin(my: 0, cpu: cpu)
                    }, label: {
                        Image("Rock")
                            .resizable()
                            .scaledToFit()
                    })
                    
                    Button(action: {
                        timerRunning = true
                        cpuRandom()
                        checkWin(my: 1, cpu: cpu)
                    }, label: {
                        Image("Scissors")
                            .resizable()
                            .scaledToFit()
                        
                    })
                    
                    Button(action: {
                        timerRunning = true
                        cpuRandom()
                        checkWin(my: 2, cpu: cpu)
                    }, label: {
                        Image("Paper")
                            .resizable()
                            .scaledToFit()
                    })
                }
                .offset(x: 0, y: 60)
                
                HStack{
                    
                    
                }
            }
            .onReceive(timer) { _ in
                if runTime>0 && timerRunning{
                    if cpu<2 {
                        cpu += 1
                    }else{
                        cpu = 0
                    }
                    runTime -= 0.1
                }else{
                    timerRunning = false
                    runTime = 1.5
                    
                }
            }
        }
    }
    func cpuRandom(){
        cpu = Int.random(in:0...2)
    }
    func checkWin(my:Int, cpu:Int){
        //0:rock 1:scissors 2: paper
        if (my==0 && cpu==1)||(my==1 && cpu==2)||(my==2 && cpu==0) {
            gameOut = "Win"
            point += money
        }else if (my==0 && cpu==0)||(my==1&&cpu==1)||(my==2 && cpu==2) {
            gameOut = "Draw"
        }else{
            gameOut = "Lose"
            point -= money
        }
        
    }
}


```
