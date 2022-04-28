import SwiftUI

struct ContentView: View {
    @State var w = CGFloat(250)
    @State var h = CGFloat(150)
    
    @State private var offset: CGSize = .zero
    @State private var position: CGSize = .zero
    
    @State private var wWin: CGFloat = 0
    @State private var hWin: CGFloat = 0
    @State private var offWin = false
    
    
    var body: some View {
        
        ZStack{
            VStack{
                Button(action: {
                    offWin.toggle()
                    
                    self.w = 250
                    self.h = 150
                }){
                    AngularGradient(gradient: Gradient(colors: [Color.clear,Color.green]), center: .center)
                        .frame(width: 100, height: 100)
                        .cornerRadius(20)
                }
            
                withAnimation(.easeIn) {
                    Circle()
                        .frame(width: wWin, height: hWin)
                        .foregroundColor(Color.gray)
                }
                
            }
            
        ZStack(alignment: .leading) {
            Color.white
            VStack{
                HStack{
                    Button(action: {
                        
                        if offWin == true{
                            self.offWin = false
                        }
                        
                        
                        self.w = 0
                        self.h = 0
                        
                        if offWin == false{
                            self.wWin = 0
                            self.hWin = 0
                        }
                    }){
                        Circle()
                            .foregroundColor(.red)
                            .frame(width: 15, height: 15)
                    }
                    Button(action: {
                        offWin.toggle()
                        
                        if offWin == false{
                            self.offWin = true
                        }
                        
                        if offWin == true{
                            self.wWin = 10
                            self.hWin = 10
                        } 
                        
                        self.w = 0
                        self.h = 0
                    }){
                        Circle()
                            .foregroundColor(.yellow)
                            .frame(width: 15, height: 15)
                    }
                        
                    Text("app")
                        .foregroundColor(.gray)
                        .padding(30)
                }
                .padding()
                
                Text("text")
                    .foregroundColor(.black)
                    .padding(20)
                Text("")
                    .padding()
            }
            
        }
        .frame(width: self.w, height: self.h)
        
        .cornerRadius(8)
        .offset(x: offset.width + position.width, y: offset.height + position.height)
        .gesture(
            DragGesture()
                .onChanged({ value in
                    withAnimation(.spring()) {
                        self.offset = value.translation
                }})
                .onEnded({ value in
                    withAnimation(.spring()) {
                        self.position.width += value.translation.width
                        self.position.height += value.translation.height
                        self.offset = .zero
                    }
                })
        )
    }
}
}
